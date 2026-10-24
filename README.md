const DEFAULT_PLAYERS = [
  { id: 1, name: 'Player 1', timeLeft: 120, active: true },
  { id: 2, name: 'Player 2', timeLeft: 120, active: false },
  { id: 3, name: 'Player 3', timeLeft: 120, active: false },
  { id: 4, name: 'Player 4', timeLeft: 120, active: false },
];

const playersEl = document.getElementById('players');
const startPauseBtn = document.getElementById('startPauseBtn');
const resetBtn = document.getElementById('resetBtn');
const applySettingsBtn = document.getElementById('applySettingsBtn');
const turnDurationInput = document.getElementById('turnDuration');
const startingTimeInput = document.getElementById('startingTime');

let players = DEFAULT_PLAYERS.map((player) => ({ ...player }));
let countdownId = null;
let isRunning = false;
let turnSeconds = Number(turnDurationInput.value);

function formatTime(totalSeconds) {
  const safeValue = Math.max(0, Math.ceil(totalSeconds));
  const minutes = Math.floor(safeValue / 60)
    .toString()
    .padStart(2, '0');
  const seconds = (safeValue % 60).toString().padStart(2, '0');
  return `${minutes}:${seconds}`;
}

function getActivePlayerIndex() {
  return players.findIndex((player) => player.active);
}

function renderPlayers() {
  playersEl.innerHTML = '';

  players.forEach((player, index) => {
    const card = document.createElement('article');
    card.className = `player-card ${player.active ? 'active' : ''}`;
    if (index !== getActivePlayerIndex()) {
      card.classList.add('out');
    }

    const timeClass = player.timeLeft <= 10 ? 'warning' : '';

    card.innerHTML = `
      <div class="player-meta">
        <div class="player-name">${player.name}</div>
        <span class="player-indicator" aria-label="Current player"></span>
      </div>
      <div class="timer ${timeClass}">${formatTime(player.timeLeft)}</div>
      <div class="player-actions">
        <button class="${player.active ? 'success' : ''}" data-action="activate" data-player-id="${player.id}">Focus</button>
        <button data-action="add" data-player-id="${player.id}">+${turnSeconds}s</button>
      </div>
    `;

    playersEl.appendChild(card);
  });
}

function togglePlayerFocus(playerId) {
  players = players.map((player) => ({
    ...player,
    active: player.id === playerId,
  }));
  renderPlayers();
}

function addTimeToPlayer(playerId, seconds) {
  players = players.map((player) => {
    if (player.id === playerId) {
      return { ...player, timeLeft: player.timeLeft + seconds };
    }
    return player;
  });

  renderPlayers();
}

function startTimer() {
  if (isRunning) {
    return;
  }

  isRunning = true;
  startPauseBtn.textContent = 'Pause';
  startPauseBtn.classList.remove('primary');
  startPauseBtn.classList.add('success');

  countdownId = setInterval(() => {
    const activeIndex = getActivePlayerIndex();
    if (activeIndex === -1) {
      return;
    }

    players = players.map((player, index) => {
      if (index === activeIndex) {
        const nextTime = player.timeLeft - 1;
        return { ...player, timeLeft: Math.max(0, nextTime) };
      }
      return player;
    });

    renderPlayers();

    if (players[activeIndex].timeLeft <= 0) {
      stopTimer();
    }
  }, 1000);
}

function stopTimer() {
  isRunning = false;
  startPauseBtn.textContent = 'Start';
  startPauseBtn.classList.remove('success');
  startPauseBtn.classList.add('primary');
  clearInterval(countdownId);
}

function resetPlayers() {
  stopTimer();
  players = DEFAULT_PLAYERS.map((player) => ({ ...player, timeLeft: Number(startingTimeInput.value) }));
  players[0].active = true;
  renderPlayers();
}

function applySettings() {
  turnSeconds = Number(turnDurationInput.value);
  const newStartingTime = Number(startingTimeInput.value);

  players = players.map((player, index) => ({
    ...player,
    timeLeft: Math.max(0, newStartingTime),
    active: index === 0,
  }));

  renderPlayers();
}

playersEl.addEventListener('click', (event) => {
  const button = event.target.closest('button');
  if (!button) {
    return;
  }

  const { action, playerId } = button.dataset;
  const numericPlayerId = Number(playerId);

  if (action === 'activate') {
    togglePlayerFocus(numericPlayerId);
  }

  if (action === 'add') {
    addTimeToPlayer(numericPlayerId, turnSeconds);
  }
});

startPauseBtn.addEventListener('click', () => {
  if (isRunning) {
    stopTimer();
    return;
  }

  startTimer();
});

resetBtn.addEventListener('click', resetPlayers);
applySettingsBtn.addEventListener('click', applySettings);

renderPlayers();

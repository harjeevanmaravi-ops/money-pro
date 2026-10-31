# money-pro
Money Pro is an online rewards platform where users can complete tasks and earn points.
<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Money Pro</title>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f1f5f9;
  color: #172033;
}

header {
  background: linear-gradient(120deg,#101c45,#1769e0);
  color: white;
  padding: 25px 18px;
  border-radius: 0 0 25px 25px;
}

header h1 {
  margin: 0;
  font-size: 28px;
}

header p {
  margin-bottom: 0;
  color: #dceaff;
}

.container {
  padding: 18px;
  max-width: 650px;
  margin: auto;
}

.balance {
  background: white;
  padding: 22px;
  border-radius: 18px;
  margin-top: -5px;
  box-shadow: 0 5px 18px #0001;
}

.balance h2 {
  margin: 5px 0;
  color: #1265db;
  font-size: 32px;
}

.points {
  color: #64748b;
}

h3 {
  margin-top: 25px;
}

.task {
  background: white;
  padding: 17px;
  margin: 13px 0;
  border-radius: 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
  box-shadow: 0 3px 12px #0001;
}

.task p {
  margin: 6px 0 0;
  color: #64748b;
  font-size: 13px;
}

button {
  border: none;
  background: #1769e0;
  color: white;
  padding: 11px 15px;
  border-radius: 9px;
  font-weight: bold;
  cursor: pointer;
}

button:disabled {
  background: #16a36a;
}

.history {
  background: white;
  padding: 17px;
  border-radius: 15px;
  margin-top: 20px;
}

footer {
  text-align: center;
  padding: 25px;
  color: #64748b;
  font-size: 12px;
}
</style>
</head>

<body>

<header>
  <h1>💰 Money Pro</h1>
  <p>Complete demo tasks and collect points!</p>
</header>

<div class="container">

  <div class="balance">
    <div class="points">Your Demo Balance</div>
    <h2><span id="balance">0</span> Points</h2>
    <p>⭐ Total Points: <b id="total">0</b></p>
  </div>

  <h3>🎯 Available Tasks</h3>

  <div class="task">
    <div>
      <b>📖 Read a Demo Article</b>
      <p>Reward: 10 Points</p>
    </div>
    <button onclick="completeTask(0)">Start</button>
  </div>

  <div class="task">
    <div>
      <b>🧠 Complete Quiz</b>
      <p>Reward: 20 Points</p>
    </div>
    <button onclick="completeTask(1)">Start</button>
  </div>

  <div class="task">
    <div>
      <b>🎮 Play Demo Game</b>
      <p>Reward: 15 Points</p>
    </div>
    <button onclick="completeTask(2)">Start</button>
  </div>

  <div class="history">
    <h3>📊 My Activity</h3>
    <p id="activity">No tasks completed yet.</p>
  </div>

</div>

<footer>
  Money Pro Demo Project<br>
  Points have no real cash value.
</footer>

<script>
let balance = 0;
let completed = [];

const rewards = [10, 20, 15];

function completeTask(id) {

  if (completed.includes(id)) {
    return;
  }

  completed.push(id);
  balance += rewards[id];

  document.getElementById("balance").innerText = balance;
  document.getElementById("total").innerText = balance;

  const buttons = document.querySelectorAll(".task button");
  buttons[id].innerText = "Completed";
  buttons[id].disabled = true;

  document.getElementById("activity").innerText =
    completed.length + " demo task(s) completed.";

}
</script>

</body>
</html>
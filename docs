<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My English Progress Tracker</title>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f7fa;
      color: #333;
      text-align: center;
      margin: 0;
      padding: 20px;
    }
    .container {
      max-width: 800px;
      margin: auto;
    }
    canvas {
      margin: 30px 0;
    }
    form {
      display: grid;
      gap: 10px;
      margin-top: 20px;
    }
    input, button {
      padding: 10px;
      font-size: 14px;
    }
    button {
      cursor: pointer;
      background: #4CAF50;
      border: none;
      color: white;
      border-radius: 5px;
    }
    button:hover {
      background: #45a049;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>📊 My English Progress Tracker</h1>
    <p>Track your progress in Writing, Speaking, Reading, Grammar, and Listening.</p>

    <canvas id="progressChart"></canvas>

    <form id="progressForm">
      <input type="number" id="writing" placeholder="Writing Score (0-100)" min="0" max="100" required>
      <input type="number" id="speaking" placeholder="Speaking Score (0-100)" min="0" max="100" required>
      <input type="number" id="reading" placeholder="Reading Score (0-100)" min="0" max="100" required>
      <input type="number" id="grammar" placeholder="Grammar Score (0-100)" min="0" max="100" required>
      <input type="number" id="listening" placeholder="Listening Score (0-100)" min="0" max="100" required>
      <button type="submit">Update Progress</button>
    </form>
  </div>

  <script>
    const ctx = document.getElementById('progressChart').getContext('2d');

    const data = {
      labels: ['Writing', 'Speaking', 'Reading', 'Grammar', 'Listening'],
      datasets: [{
        label: 'My Progress (%)',
        data: [0, 0, 0, 0, 0],
        backgroundColor: 'rgba(54, 162, 235, 0.2)',
        borderColor: 'rgba(54, 162, 235, 1)',
        borderWidth: 2,
        pointBackgroundColor: 'rgba(54, 162, 235, 1)'
      }]
    };

    const config = {
      type: 'radar',
      data: data,
      options: {
        scales: {
          r: {
            suggestedMin: 0,
            suggestedMax: 100,
            ticks: {
              stepSize: 20
            }
          }
        }
      }
    };

    const progressChart = new Chart(ctx, config);

    document.getElementById('progressForm').addEventListener('submit', function(e) {
      e.preventDefault();
      const writing = document.getElementById('writing').value;
      const speaking = document.getElementById('speaking').value;
      const reading = document.getElementById('reading').value;
      const grammar = document.getElementById('grammar').value;
      const listening = document.getElementById('listening').value;

      progressChart.data.datasets[0].data = [writing, speaking, reading, grammar, listening];
      progressChart.update();
    });
  </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Fortune Cookie</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: #fff8e1;
      text-align: center;
      padding: 50px;
    }

    h1 {
      font-size: 2em;
      margin-bottom: 20px;
      color: #8b4513;
    }

    #cookie {
      width: 200px;
      cursor: pointer;
      transition: transform 0.3s ease;
    }

    #cookie:hover {
      transform: scale(1.05);
    }

    #fortune {
      margin-top: 30px;
      font-size: 1.5em;
      color: #444;
      opacity: 0;
      transition: opacity 0.8s ease;
    }

    .visible {
      opacity: 1;
    }

    #reset-btn {
      display: none;
      margin-top: 20px;
      padding: 10px 20px;
      background-color: #f5c26b;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
    }

    #reset-btn:hover {
      background-color: #f7a733;
    }
  </style>
</head>
<body>

  <h1>Click the Fortune Cookie 🍪</h1>
  <img id="cookie" src="https://i.imgur.com/2XhZbYp.png" alt="Fortune Cookie">
  <div id="fortune"></div>
  <button id="reset-btn">Try Again</button>

  <script>
    const fortunes = [
      "You will have a pleasant surprise soon.",
      "A thrilling opportunity is near.",
      "Happiness is around the corner.",
      "An unexpected windfall is coming.",
      "Now is the perfect time to try something new.",
      "Your kindness will return to you this week.",
      "Adventure awaits you — don’t be late.",
      "Someone is thinking of you right now.",
      "A dream you have will soon come true.",
      "Big change is coming. Embrace it!"
    ];

    const cookie = document.getElementById('cookie');
    const fortuneText = document.getElementById('fortune');
    const resetBtn = document.getElementById('reset-btn');

    cookie.addEventListener('click', () => {
      const randomIndex = Math.floor(Math.random() * fortunes.length);
      const fortune = fortunes[randomIndex];
      fortuneText.textContent = `"${fortune}"`;
      fortuneText.classList.add('visible');
      resetBtn.style.display = 'inline-block';
      cookie.style.pointerEvents = 'none';
    });

    resetBtn.addEventListener('click', () => {
      fortuneText.textContent = '';
      fortuneText.classList.remove('visible');
      resetBtn.style.display = 'none';
      cookie.style.pointerEvents = 'auto';
    });
  </script>

</body>
</html>

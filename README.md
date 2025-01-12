<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hey Stander, It's Your Birthday</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #ff9a9e, #fad0c4);
            color: #333;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
        }
        header {
            text-align: center;
            padding: 20px;
        }
        header h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
        }
        header p {
            font-size: 1.2em;
            margin-top: 0;
        }
        .main-container {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
            width: 80%;
            max-width: 1200px;
        }
        .image {
            width: 40%;
            max-width: 300px;
        }
        .puzzle-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            width: 80%;
            max-width: 1200px;
            margin-top: 20px;
        }
        .puzzle {
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            padding: 20px;
            text-align: center;
            transition: transform 0.3s;
        }
        .puzzle:hover {
            transform: translateY(-5px);
        }
        .puzzle h2 {
            font-size: 1.5em;
            margin-bottom: 15px;
        }
        .puzzle p {
            font-size: 1em;
            margin-bottom: 15px;
        }
        .puzzle button {
            background: #ff6b6b;
            color: #fff;
            border: none;
            border-radius: 5px;
            padding: 10px 15px;
            font-size: 1em;
            cursor: pointer;
            transition: background 0.3s;
        }
        .puzzle button:hover {
            background: #e63946;
        }
        .puzzle[disabled] {
            opacity: 0.5;
            pointer-events: none;
        }
        footer {
            margin-top: 20px;
            text-align: center;
            font-size: 0.9em;
            color: #555;
        }
    </style>
</head>
<body>
    <header>
        <h1>Hey Stander, It's Your Birthday!</h1>
        <p>Complete the following puzzles to reveal the secret message.</p>
    </header>
    <div class="main-container">
        <img src="left-image.jpg" alt="Left Image" class="image">
        <img src="right-image.jpg" alt="Right Image" class="image">
    </div>
    <main class="puzzle-container">
        <div class="puzzle" id="puzzle1">
            <h2>Puzzle 1</h2>
            <p>Solve this riddle to get the first piece of the message.</p>
            <button onclick="unlockNext(1)">Solve</button>
        </div>
        <div class="puzzle" id="puzzle2" disabled>
            <h2>Puzzle 2</h2>
            <p>Match the pairs to uncover the next part.</p>
            <button onclick="unlockNext(2)" disabled>Solve</button>
        </div>
        <div class="puzzle" id="puzzle3" disabled>
            <h2>Puzzle 3</h2>
            <p>Decode the cipher for the final piece.</p>
            <button onclick="unlockNext(3)" disabled>Solve</button>
        </div>
    </main>
    <footer>
        <p>&copy; 2025 Happy Birthday, Stander! 🎉</p>
    </footer>

    <script>
        function unlockNext(puzzleNumber) {
            const currentPuzzle = document.getElementById(`puzzle${puzzleNumber}`);
            currentPuzzle.querySelector('button').textContent = 'Solved';
            currentPuzzle.querySelector('button').disabled = true;

            if (puzzleNumber < 3) {
                const nextPuzzle = document.getElementById(`puzzle${puzzleNumber + 1}`);
                nextPuzzle.removeAttribute('disabled');
                nextPuzzle.querySelector('button').removeAttribute('disabled');
            }
        }
    </script>
</body>
</html>

# MEA-FINAL-PROJECT
Final Project By
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random Generator Hub</title>
    
  <style>
    /* Reset default margins and set up a clean font */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #1e1e2f, #2a2a40);
            color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        /* Main card container */
        .container {
            background: #22223b;
            padding: 2.5rem;
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            text-align: center;
            max-width: 500px;
            width: 90%;
        }

        h1 {
            font-size: 2.2rem;
            margin-bottom: 0.5rem;
            color: #4ea8de;
        }

        .subtitle {
            color: #a0a0c0;
            font-size: 0.95rem;
            margin-bottom: 2rem;
        }

        /* Box where the random text appears */
        .display-box {
            background: #121225;
            padding: 1.5rem;
            border-radius: 8px;
            min-height: 120px;
            display: flex;
            justify-content: center;
            align-items: center;
            border-left: 5px solid #4ea8de;
            margin-bottom: 2rem;
        }

        #output-text {
            font-size: 1.1rem;
            line-height: 1.6;
            color: #e0e0ff;
        }

        /* Buttons configuration */
        .button-group {
            display: flex;
            gap: 1rem;
            justify-content: center;
        }

        .btn {
            background: #4ea8de;
            color: #121225;
            border: none;
            padding: 0.8rem 1.5rem;
            font-size: 1rem;
            font-weight: bold;
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        .btn:hover {
            background: #56cfe1;
            transform: translateY(-2px);
        }

        #fact-btn {
            background: #72efdd;
        }

        #fact-btn:hover {
            background: #64dfdf;
        }
    </style>
</head>
<body>

   <div class="container">
        <h1>🔀 The Random Hub</h1>
        <p class="subtitle">Need a laugh or a quick brain flex? Choose your vibe below!</p>
          <div class="display-box">
            <p id="output-text">Click a button below to generate something awesome!</p>
        </div>
  <div class="button-group">
            <button id="joke-btn" class="btn">Tell Me a Joke 😂</button>
            <button id="fact-btn" class="btn">Give Me a Fact 🧠</button>
        </div>
    </div>

  <script>
        // Array of random jokes
        const jokes = [
            "Why don't scientists trust atoms? Because they make up everything!",
            "What do you call a fake noodle? An impasta.",
            "Why did the scarecrow win an award? Because he was outstanding in his field!",
            "How does a penguin build its house? Igloos it together.",
            "Why don't skeletons fight each other? They don't have the guts.",
            "What do you call a factory that makes okay products? A satisfactory."
        ];

        // Array of random facts
        const facts = [
            "Bananas are berries, but strawberries aren't!",
            "Honey never spoils. You could theoretically eat 3,000-year-old Egyptian tomb honey.",
            "Wombat poop is cube-shaped, which stops it from rolling away.",
            "A day on Venus is longer than a year on Venus.",
            "Sloths can hold their breath longer than dolphins can.",
            "The total weight of all the ants on Earth is roughly equal to the total weight of all humans."
        ];

        // Get elements from the HTML
        const outputText = document.getElementById("output-text");
        const jokeBtn = document.getElementById("joke-btn");
        const factBtn = document.getElementById("fact-btn");

        // Function to get a random item from an array
        function getRandomItem(array) {
            const randomIndex = Math.floor(Math.random() * array.length);
            return array[randomIndex];
        }

        // Event listener for the Joke button
        jokeBtn.addEventListener("click", () => {
            const randomJoke = getRandomItem(jokes);
            outputText.textContent = randomJoke;
        });

        // Event listener for the Fact button
        factBtn.addEventListener("click", () => {
            const randomFact = getRandomItem(facts);
            outputText.textContent = randomFact;
        });
    </script>
</body>
</html>

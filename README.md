 <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hindi to Nepali Translation</title>
    <style>
        :root {
            --box-width: 100%; /* Default width of textarea and output box */
            --box-height: 37.5px; /* Default height of textarea and output box */
            --button-width: 100%; /* Default width of button */
            --button-height: 50px; /* Default height of button */
        }

        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #24292d; /* Set background color to black */
            color: white; /* Set text color to white for contrast */
        }
        .translation-box {
            max-width: 300px;
            margin: auto;
        }
        textarea, #output {
            width: var(--box-width);
            padding: 10px;
            margin-top: 10px;
            font-size: 16px;
            height: var(--box-height);
            box-sizing: border-box;
        }
        button {
            width: var(--button-width);
            padding: 10px;
            margin-top: 10px;
            font-size: 16px;
            height: var(15px);
            cursor: pointer;
        }
        #output {
            margin-top: 10px;
            padding: 10px;
            background-color: #333; /* Darker background color for output */
            color: white; /* Set text color to white */
            border: 1px solid #555; /* Darker border color */
            min-height: var(--box-height); /* Ensure min-height is equal to the textarea height */
            text-align: center; /* Center text in the output box */
        }
    </style>
</head>


<body>
    <div class="translation-box">
        <h3>Hindi to Nepali Translator</h3>
        <textarea id="hindiInput" rows="5" placeholder="Enter Hindi text here..."></textarea>
        <button onclick="translateToNepali()">Click To Translate</button>
        <div id="output"></div>
    </div>
    <script>
        function translateToNepali() {
            var hindiText = document.getElementById('hindiInput').value;
            var nepaliText = "";
            var dictionary = {
                'नमस्ते': 'नमस्ते',
                'आप': 'तपाईं',
                'कैसे': 'कसरी',
                'हैं': 'हुनुहुन्छ',
                'मैं': 'म',
                'ठीक': 'ठीक',
                'हूँ': 'छु',
                'क्या': 'के',
                'यह': 'यो',
                'है': 'छ',
            };
            var words = hindiText.split(/\s+/);
            for (var i = 0; i < words.length; i++) {
                var word = words[i];
                if (dictionary.hasOwnProperty(word)) {
                    nepaliText += dictionary[word] + " ";
                } else {
                    nepaliText += word + " ";
                }
            }
            document.getElementById('output').innerHTML = nepaliText.trim();
        }
    </script>
</body>
</html>

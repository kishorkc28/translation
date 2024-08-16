<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hindi to Nepali Translation</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; }
        .translation-box { max-width: 500px; margin: auto; }
        textarea, button { width: 100%; padding: 10px; margin-top: 10px; font-size: 16px; }
        #output { margin-top: 10px; padding: 10px; background-color: #f9f9f9; border: 1px solid #ddd; min-height: 100px; }
    </style>
</head>
<body>
    <div class="translation-box">
        <h2>Hindi to Nepali Translator</h2>
        <textarea id="hindiInput" rows="5" placeholder="Enter Hindi text here..."></textarea>
        <button onclick="translateToNepali()">Translate</button>
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

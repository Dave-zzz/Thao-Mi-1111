Ich liebe dich Thao Mi 
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Für meine Thao Mi</title>
    <style>
        body {
            background-color: black;
            color: white;
            text-align: center;
            font-family: 'Arial', sans-serif;
            overflow: hidden;
        }
        h1 {
            font-size: 3em;
            color: red;
            opacity: 0;
            animation: fadeIn 3s forwards;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.8); }
            to { opacity: 1; transform: scale(1); }
        }
        .message {
            font-size: 2em;
            font-family: 'Cursive', sans-serif;
            margin-top: 20px;
        }
        .hearts {
            position: absolute;
            width: 100%;
            height: 100vh;
            overflow: hidden;
        }
        .heart {
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: red;
            clip-path: polygon(50% 0%, 100% 35%, 80% 100%, 50% 80%, 20% 100%, 0% 35%);
            animation: float 5s infinite;
        }
        @keyframes float {
            0% { transform: translateY(100vh) scale(0.5); }
            100% { transform: translateY(-10vh) scale(1.2); }
        }
        .options {
            display: none;
        }
        .teddy {
            display: none;
            position: relative;
            width: 200px;
            margin: 20px auto;
        }
        .speech-bubble {
            display: none;
            position: relative;
            background: white;
            color: black;
            padding: 10px;
            border-radius: 10px;
            margin: auto;
            width: 200px;
        }
    </style>
</head>
<body>
    <h1>Für meine Thao Mi</h1>
    <p class="message">Ich liebe dich über alles, Schatz</p>
    <p class="message">Willst du meine Valentine sein?</p>
    <div class="hearts"></div>
    
    <div class="options">
        <button onclick="yesClicked()">Ja</button>
        <button onclick="noClicked()">Nein</button>
    </div>
    
    <img src="teddy_happy.png" class="teddy" id="teddy">
    <div class="speech-bubble" id="speech">Thao Mi, sag bitte ja!</div>
    
    <script>
        document.addEventListener("DOMContentLoaded", function() {
            setTimeout(() => {
                document.querySelector(".hearts").style.display = "none";
                document.querySelector(".options").style.display = "block";
                document.getElementById("teddy").style.display = "block";
                document.getElementById("speech").style.display = "block";
            }, 5000);
        });
        
        function noClicked() {
            document.getElementById("teddy").src = "teddy_sad.png";
            document.getElementById("speech").innerText = "Kannst du bitte noch mal drüber nachdenken?";
            setTimeout(() => {
                document.querySelector("button:last-child").style.display = "none";
                document.querySelector("button:first-child").style.fontSize = "2em";
            }, 3000);
        }
        
        function yesClicked() {
            document.getElementById("teddy").src = "teddy_happy.png";
            document.body.style.backgroundColor = "black";
            document.body.innerHTML = "<h1 style='color:white;'>Ich freue mich so sehr, Thao Mi!</h1>";
        }
    </script>
</body>
</html>

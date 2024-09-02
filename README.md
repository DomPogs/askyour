<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crush Mo Ba Ako?</title>
    <style>
        body {
            background: linear-gradient(to right, #ffafbd, #ffc3a0);
            font-family: 'Arial', sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
        }
        .central-box {
            border: 2px solid #ff66b2;
            border-radius: 15px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.9);
            box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.2);
            width: 300px;
            text-align: center;
            position: relative;
            backdrop-filter: blur(10px);
        }
        .button {
            margin: 10px;
            padding: 15px 30px;
            font-size: 18px;
            cursor: pointer;
            border-radius: 25px;
            border: 2px solid;
            transition: all 0.3s ease;
            position: relative;
            outline: none;
        }
        .button-yes {
            border-color: #4a90e2;
            color: #4a90e2;
            background: #eaf4fe;
        }
        .button-no {
            border-color: #e94e77;
            color: #e94e77;
            background: #fef2f2;
        }
        .button-yes:hover {
            background: #4a90e2;
            color: #fff;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
        }
        .button-no:hover {
            background: #e94e77;
            color: #fff;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
        }
        .credit {
            position: absolute;
            bottom: 10px;
            right: 10px;
            font-size: 14px;
            color: #888;
            font-style: italic;
        }
        h2 {
            color: #ff66b2;
        }
    </style>
</head>
<body>
    <div class="central-box">
        <img id="crush-image" src="sweet.gif" alt="Crush Image" width="100%" height="auto">
        <h2 id="message">Hi Crush mo ba ako?</h2>
        <button class="button button-yes" onclick="yesClicked()">Yes</button>
        <button class="button button-no" onclick="moveButtonNo()">No</button>
    </div>

    <div class="credit">Created by Dominique E</div>

    <script>
        // Paths to your images and music
        let initialImage = 'sweet.gif';
        let yesImage = 'love.gif';
        let musicFile = 'Kilig1.mp3';

        function yesClicked() {
            const centralBox = document.querySelector('.central-box');
            centralBox.innerHTML = `
                <img id="crush-image" src="${yesImage}" alt="Crush Image" width="100%" height="auto">
                <h2>Crush rin kita yiee</h2>
            `;
            playMusic();
        }

        function moveButtonNo() {
            let buttonNo = document.querySelector('.button-no');
            let moveX = Math.floor(Math.random() * (window.innerWidth - buttonNo.offsetWidth));
            let moveY = Math.floor(Math.random() * (window.innerHeight - buttonNo.offsetHeight));
            buttonNo.style.position = 'absolute';
            buttonNo.style.left = moveX + 'px';
            buttonNo.style.top = moveY + 'px';
        }

        function playMusic() {
            let audio = new Audio(musicFile);
            audio.play();
        }
    </script>
</body>
</html>

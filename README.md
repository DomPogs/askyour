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
        .image {
            width: 100%;
            height: auto;
            border-radius: 15px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
        }
    </style>
</head>
<body>
    <div class="central-box">
        <img id="crush-image" src="sweet.gif" alt="Crush Image" class="image">
        <h2 id="message">Hi Crush mo ba ako?</h2>
        <button class="button button-yes" onclick="yesClicked()">Yes</button>
        <button class="button button-no" onclick="moveButtonNo()">No</button>
    </div>

    <div class="credit">Created by Dominique E</div>

    <script>
        // Paths to your images and music
        const images = {
            initial: 'sweet.gif',
            yes: 'love.gif'
        };
        const musicFile = 'Kilig1.mp3';
        const moveDistance = 192; // 2 inches in pixels (96px per inch)

        function yesClicked() {
            const image = document.getElementById('crush-image');
            image.src = images.yes;
            const message = document.getElementById('message');
            message.innerText = 'Crush rin kita yiee';
            playMusic();
            removeButtons();
        }

        function moveButtonNo() {
            const buttonNo = document.querySelector('.button-no');
            const maxX = window.innerWidth - buttonNo.offsetWidth;
            const maxY = window.innerHeight - buttonNo.offsetHeight;

            // Generate random movement within a 2-inch radius
            const moveX = Math.random() * moveDistance - (moveDistance / 2);
            const moveY = Math.random() * moveDistance - (moveDistance / 2);

            let currentLeft = buttonNo.offsetLeft + moveX;
            let currentTop = buttonNo.offsetTop + moveY;

            // Ensure the button stays within the window bounds
            if (currentLeft < 0) currentLeft = 0;
            if (currentTop < 0) currentTop = 0;
            if (currentLeft + buttonNo.offsetWidth > window.innerWidth) currentLeft = window.innerWidth - buttonNo.offsetWidth;
            if (currentTop + buttonNo.offsetHeight > window.innerHeight) currentTop = window.innerHeight - buttonNo.offsetHeight;

            buttonNo.style.position = 'absolute';
            buttonNo.style.left = `${currentLeft}px`;
            buttonNo.style.top = `${currentTop}px`;
        }

        function removeButtons() {
            const yesButton = document.querySelector('.button-yes');
            const noButton = document.querySelector('.button-no');
            if (yesButton) yesButton.style.display = 'none';
            if (noButton) noButton.style.display = 'none';
        }

        function playMusic() {
            const audio = new Audio(musicFile);
            audio.play();
        }
    </script>
</body>
</html>

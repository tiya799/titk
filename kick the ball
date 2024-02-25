<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mini Game JavaScript</title>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: #f0f0f0;
        }
        #player {
            position: absolute;
            left: 50%;
            bottom: 10px;
            transform: translateX(-50%);
            width: 100px;
            height: 20px;
            background-color: black;
        }
        #ball {
            position: absolute;
            left: 50%;
            top: 0;
            transform: translateX(-50%);
            width: 20px;
            height: 20px;
            background-color: blue;
        }
    </style>
</head>
<body>
    <div id="player"></div>
    <div id="ball"></div>

    <script>
        const player = document.getElementById('player');
        const ball = document.getElementById('ball');
        let ballSpeed = 5;
        let ballDirection = 1;
        let playerPosition = 50;

        document.addEventListener('keydown', function(event) {
            if (event.key === 'ArrowLeft' && playerPosition > 0) {
                playerPosition -= 10;
                player.style.left = playerPosition + '%';
            } else if (event.key === 'ArrowRight' && playerPosition < 100) {
                playerPosition += 10;
                player.style.left = playerPosition + '%';
            }
        });

        function moveBall() {
            let ballTop = ball.offsetTop;
            if (ballTop + ballSpeed * ballDirection < window.innerHeight - 20) {
                ball.style.top = ballTop + ballSpeed * ballDirection + 'px';
            } else {
                if (ballTop + ballSpeed * ballDirection >= window.innerHeight - 20 && 
                    ballTop + ballSpeed * ballDirection <= window.innerHeight) {
                    if (ballTop + ballSpeed * ballDirection < window.innerHeight - 10) {
                        ballDirection = -ballDirection;
                    }
                } else {
                    ballDirection = -ballDirection;
                }
            }
        }

        function gameLoop() {
            moveBall();
            requestAnimationFrame(gameLoop);
        }

        gameLoop();
    </script>
</body>
</html>

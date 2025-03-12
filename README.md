
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hack UI</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; font-family: Arial, sans-serif; }
        body { background: black; overflow: hidden; }
        
        iframe {
            position: fixed; top: 0; left: 0; width: 100%; height: 100%; border: none;
        }

        #open { 
            position: fixed; bottom: 50px; right: 50px;
            width: 150px; height: 50px; display: flex; align-items: center; justify-content: center;
            background: linear-gradient(45deg, #ff0000, #ff7300);
            color: #fff; font-size: 16px; font-weight: bold; border: none; cursor: pointer;
            border-radius: 50px; box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            user-select: none;
        }

        #open span { margin-left: 8px; }

        #dialogBox {
            position: fixed; top: 50%; left: 50%; transform: translate(-50%, -50%);
            background: rgba(255, 255, 255, 0.1); 
            backdrop-filter: blur(12px);
            border: 2px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 4px 20px rgba(255, 255, 255, 0.2);
            color: white; padding: 20px;
            width: 300px; border-radius: 15px; text-align: center;
            display: none; animation: fadeIn 0.3s;
        }

        #dialogBox h2 {
            font-size: 22px; text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 10px;
        }

        .dialog-content {
            font-size: 16px; line-height: 1.5; color: #eee;
            text-shadow: 0 0 5px rgba(255, 255, 255, 0.3);
        }

        .highlight { color: #ffcc00; font-weight: bold; }

        #closeBtn {
            margin-top: 15px; padding: 10px;
            background: #ff4444; border: none;
            color: white; font-weight: bold; cursor: pointer;
            width: 100%; border-radius: 8px;
            transition: 0.3s;
        }

        #closeBtn:hover { background: #ff0000; }

        #telegramBtn {
            display: block; margin-top: 15px; padding: 12px;
            background: #0088cc; color: white;
            font-size: 16px; font-weight: bold;
            text-decoration: none; border-radius: 8px;
            transition: 0.3s;
        }

        #telegramBtn:hover { background: #006699; }

        #periodNumber { font-size: 18px; font-weight: bold; color: #ffcc00; }
        #timerText { font-size: 20px; color: #00ff00; margin: 8px 0; }

        #resultText {
            font-size: 22px; font-weight: bold;
            text-transform: uppercase;
            animation: glowEffect 0.8s infinite alternate;
        }

        .big { color: #00ff00; }
        .small { color: #ff0000; }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        @keyframes glowEffect { from { text-shadow: 0 0 10px #fff; } to { text-shadow: 0 0 20px #fff; } }

        #copyright {
            font-size: 10px; text-align: center; color: white;
            position: fixed; bottom: 5px; width: 100%;
        }
        
    </style>
</head>
<body>

    <iframe src="http://www.14sikkim.com/#/register?invitationCode=152324554803"></iframe>

    
    <button id="open">🚀 Open Hack</button>

    <div id="dialogBox">
        <h2>🔐 Hack Panel</h2>
        <p class="dialog-content">⏳ Timer: <span id="timerText"></span></p>
        <p class="dialog-content">📅 Period: <span id="periodNumber"></span></p>
        <p class="dialog-content">🔮 Prediction: <span id="resultText"></span></p>

        <a id="telegramBtn" href="https://t.me/hamstar_key_bot/620" target="_blank">Join Telegram</
    a>

        <p class="dialog-content highlight">New account ⚠️ ₹1000 deposit करें, तभी hack work करेगा!</p>

        <button id="closeBtn">Close</button>
    </div>

    <script>
        let openBtn = document.getElementById("open");
        let dialogBox = document.getElementById("dialogBox");
        let closeBtn = document.getElementById("closeBtn");

        openBtn.onclick = () => { dialogBox.style.display = "block"; };
        closeBtn.onclick = () => { dialogBox.style.display = "none"; };

        function updatePeriodAndTimer() {
            let now = new Date();
            let year = now.getUTCFullYear();
            let month = String(now.getUTCMonth() + 1).padStart(2, '0');
            let day = String(now.getUTCDate()).padStart(2, '0');
            let hours = now.getUTCHours();
            let minutes = now.getUTCMinutes();
            let totalMinutes = hours * 60 + minutes;

            let periodNum = `${year}${month}${day}1000${10001 + totalMinutes}`;
            document.getElementById("periodNumber").innerText = periodNum;

            let lastTwoDigits = periodNum.slice(-2);
            let sum = [...lastTwoDigits].reduce((a, b) => a + parseInt(b), 0);
            if (sum > 9) sum = [...String(sum)].reduce((a, b) => a + parseInt(b), 0);

            let result = sum >= 5 ? "BIG" : "SMALL";
            document.getElementById("resultText").innerHTML = `<span class="${sum >= 5 ? 'big' : 'small'}">${result}</span>`;

            let seconds = now.getUTCSeconds();
            let remainingSeconds = 60 - seconds;
            document.getElementById("timerText").innerText = `00:${String(remainingSeconds).padStart(2, '0')}`;
        }

        setInterval(updatePeriodAndTimer, 1000);
        updatePeriodAndTimer();

        setTimeout(() => {
            let encoded = atob("Q29weXJpZ2h0ZWQgYnkgQXBrTW9kZGVyS2luZw==");
            console.log("%c" + encoded, "color: red; font-size: 16px; font-weight: bold;");
            document.body.insertAdjacentHTML("beforeend", `<p id="copyright">${encoded}</p>`);
        }, 1000);
    </script>

</body>
</html>


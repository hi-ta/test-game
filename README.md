# test-game
簡単なゲームをchatGPTで作ってみました！

<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>数当てゲーム</title>
</head>
<body>
    <h1>数当てゲーム</h1>
    <p>1から100までの数字を当ててみてね！</p>
    <input type="number" id="guess" placeholder="数字を入力してね">
    <button onclick="checkGuess()">当てる！</button>
    <p id="message"></p>

    <script>
        const numberToGuess = Math.floor(Math.random() * 100) + 1;
        let attempts = 0;

        function checkGuess() {
            const playerGuess = parseInt(document.getElementById('guess').value);
            attempts++;
            let message = '';

            if (playerGuess < numberToGuess) {
                message = 'もっと大きい数字だよ。';
            } else if (playerGuess > numberToGuess) {
                message = 'もっと小さい数字だよ。';
            } else {
                message = `おめでとう！ ${attempts} 回で当てたね！`;
            }

            document.getElementById('message').innerText = message;
        }
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Jogo do Clique</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, sans-serif;
}

body{
    background:#222;
    color:white;
    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;
    height:100vh;
}

h1{
    margin-bottom:10px;
}

#score{
    font-size:24px;
    margin-bottom:20px;
}

#game{
    width:600px;
    height:400px;
    background:white;
    position:relative;
    border-radius:10px;
    overflow:hidden;
}

#target{
    width:50px;
    height:50px;
    background:red;
    position:absolute;
    border-radius:8px;
    cursor:pointer;
    transition:0.1s;
}
</style>
</head>
<body>

<h1>🎯 Jogo do Clique</h1>
<div id="score">Pontos: 0</div>

<div id="game">
    <div id="target"></div>
</div>

<script>
const target = document.getElementById("target");
const game = document.getElementById("game");
const scoreText = document.getElementById("score");

let score = 0;

function moveTarget(){
    const maxX = game.clientWidth - target.clientWidth;
    const maxY = game.clientHeight - target.clientHeight;

    const x = Math.random() * maxX;
    const y = Math.random() * maxY;

    target.style.left = x + "px";
    target.style.top = y + "px";
}

target.addEventListener("click", () => {
    score++;
    scoreText.textContent = "Pontos: " + score;
    moveTarget();
});

setInterval(moveTarget, 1000);

moveTarget();
</script>

</body>
</html>

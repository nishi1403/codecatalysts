<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rock, Paper, Scissors Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #854F6C;
        }

        #game-container {
            display: flex;
            flex-direction: row;
            justify-content: space-evenly;
          
        }
        

        #result {
            font-size: 30px;
            margin-top: 50px;
            font-family: cursive;
            color:#190019;
            font-family: fantasy;
        }
        .common{
          background-color:#DFB6B2;
          font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande',               'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
          width:100px;
          height:50px;
          
        }
        h1{
          background-image: url('https://static.vecteezy.com/system/resources/thumbnails/000/691/497/small/rock-paper-scissors-neon-icons.jpg' );
          height:170px;
          color:#FBE4D8;
        }
        .common:hover{
          background-color:#86A8CF;
          font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-              serif;
         
        }
    
      
    </style>
</head>
<body>
    <h1>Rock, Paper, Scissors Game</h1>
    <div id="game-container">
        <button class="common" id="rock">Rock</button>
        <button  class="common" id="paper">Paper</button>
        <button  class="common" id="scissors">Scissors</button>
        
    </div>
        <p id="result"></p>
    <script>
        const choices = ["rock", "paper", "scissors"];

        const buttons = document.querySelectorAll("button");
        const resultDisplay = document.getElementById("result");

        buttons.forEach((button) => {
            button.addEventListener("click", () => {
                const playerChoice = button.id;
                const computerChoice = choices[Math.floor(Math.random() * 3)];

                const result = determineWinner(playerChoice, computerChoice);

                resultDisplay.textContent = `You chose ${playerChoice}. Computer chose ${computerChoice}. ${result}`;
            });
        });

        function determineWinner(playerChoice, computerChoice) {
            if (playerChoice === computerChoice) {
                return "It's a tie!";
            } else if (
                (playerChoice === "rock" && computerChoice === "scissors") ||
                (playerChoice === "paper" && computerChoice === "rock") ||
                (playerChoice === "scissors" && computerChoice === "paper")
            ) {
                return "You win!";
            } else {
                return "Computer wins!";
            }
        }
    </script>
</body>
</html>


<!DOCTYPE html>
<html>
<head>
    <title>TAR AI - Game Intelligence</title>
    <style>
        body {
            background: linear-gradient(135deg, #0f0f1a, #1a1a2e);
            color: white;
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 0;
            padding: 0;
        }

        h1 {
            margin-top: 30px;
            font-size: 40px;
            color: #00f2ff;
        }

        #chatbox {
            width: 80%;
            max-width: 600px;
            margin: 30px auto;
            background: #111;
            border-radius: 15px;
            padding: 20px;
            height: 400px;
            overflow-y: auto;
            box-shadow: 0 0 20px #00f2ff33;
        }

        .user {
            text-align: right;
            margin: 10px;
            color: #00ffcc;
        }

        .tar {
            text-align: left;
            margin: 10px;
            color: #ff4dff;
        }

        input {
            width: 70%;
            padding: 10px;
            border-radius: 10px;
            border: none;
            margin-bottom: 20px;
        }

        button {
            padding: 10px 20px;
            border-radius: 10px;
            border: none;
            background: #00f2ff;
            font-weight: bold;
            cursor: pointer;
        }

        button:hover {
            background: #00c4cc;
        }
    </style>
</head>

<body>

<h1>TAR AI</h1>

<div id="chatbox"></div>

<input type="text" id="userInput" placeholder="Ask about any game...">
<button onclick="talk()">Send</button>

<script>

function talk() {
    let input = document.getElementById("userInput").value;
    let chatbox = document.getElementById("chatbox");

    chatbox.innerHTML += `<div class='user'>${input}</div>`;

    let response = getResponse(input.toLowerCase());

    chatbox.innerHTML += `<div class='tar'>${response}</div>`;

    document.getElementById("userInput").value = "";
    chatbox.scrollTop = chatbox.scrollHeight;
}

function getResponse(input) {

    if (input.includes("minecraft")) {
        return "Minecraft is about survival, creativity, and progression. What do you want to know?";
    }

    if (input.includes("roblox")) {
        return "Roblox is a platform with millions of games. Are you building or playing?";
    }

    if (input.includes("fortnite")) {
        return "Fortnite rewards positioning and smart rotations. Build control wins fights.";
    }

    if (input.includes("boss")) {
        return "Boss mechanics usually include phases, patterns, and scaling difficulty.";
    }

    return "I analyze games. Ask me about any game mechanics, strategy, or progression.";
}

</script>

</body>
</html>

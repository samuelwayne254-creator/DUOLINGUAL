# DUOLINGUAL
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Language Tutor App</title>
<style>
    body {
        margin: 0;
        font-family: Arial, sans-serif;
        color: white;
        text-align: center;
        transition: background 0.5s ease-in-out;
        background-size: cover;
        background-position: center;
    }

    header {
        background: rgba(0,0,0,0.6);
        padding: 20px;
        font-size: 24px;
    }

    select, button, input {
        padding: 10px;
        margin: 10px;
        border-radius: 8px;
        border: none;
        font-size: 16px;
    }

    .container {
        background: rgba(0,0,0,0.6);
        margin: 20px;
        padding: 20px;
        border-radius: 12px;
    }

    iframe {
        width: 80%;
        height: 300px;
        border-radius: 10px;
    }

    .chat-box {
        max-width: 500px;
        margin: auto;
        text-align: left;
        height: 200px;
        overflow-y: auto;
        background: rgba(255,255,255,0.1);
        padding: 10px;
        border-radius: 10px;
    }

    .message {
        margin: 5px 0;
    }

    .user { color: #00ffcc; }
    .bot { color: #ffcc00; }

    .quiz-question {
        font-size: 18px;
        margin-bottom: 10px;
    }
</style>
</head>

<body>

<header>
🌍 Language Tutor Web App
</header>

<div class="container">
    <h2>Select Language</h2>
    <select id="languageSelect" onchange="changeLanguage()">
        <option value="france">French</option>
        <option value="japan">Japanese</option>
        <option value="spain">Spanish</option>
    </select>
</div>

<div class="container">
    <h2>🎥 Learning Video</h2>
    <iframe id="videoFrame" src="https://www.youtube.com/embed/d9I3L9bZ0jA"></iframe>
</div>

<div class="container">
    <h2>🎮 Vocabulary Game</h2>
    <div class="quiz-question" id="question"></div>
    <button onclick="checkAnswer('a')">A</button>
    <button onclick="checkAnswer('b')">B</button>
    <button onclick="checkAnswer('c')">C</button>
    <p id="result"></p>
</div>

<div class="container">
    <h2>🤖 AI Language Coach</h2>
    <div class="chat-box" id="chatBox"></div>
    <input type="text" id="userInput" placeholder="Ask something...">
    <button onclick="sendMessage()">Send</button>
</div>

<script>
const backgrounds = {
    france: "url('https://images.unsplash.com/photo-1502602898657-3e91760cbb34')",
    japan: "url('https://images.unsplash.com/photo-1505060894801-7e78c8d1a8d6')",
    spain: "url('https://images.unsplash.com/photo-1505739771075-6a33f4c5e0e7')"
};

const videos = {
    france: "https://www.youtube.com/embed/d9I3L9bZ0jA",
    japan: "https://www.youtube.com/embed/M0c6f7d3Xxk",
    spain: "https://www.youtube.com/embed/8Q0V9z4fYhE"
};

function changeLanguage() {
    const lang = document.getElementById("languageSelect").value;
    document.body.style.backgroundImage = backgrounds[lang];
    document.getElementById("videoFrame").src = videos[lang];
    loadQuestion(lang);
}

// Quiz data
const quizData = {
    france: {
        q: "What is 'Hello' in French?",
        options: {a:"Hola", b:"Bonjour", c:"Ciao"},
        correct: "b"
    },
    japan: {
        q: "What is 'Thank you' in Japanese?",
        options: {a:"Arigato", b:"Gracias", c:"Merci"},
        correct: "a"
    },
    spain: {
        q: "What is 'Goodbye' in Spanish?",
        options: {a:"Adiós", b:"Au revoir", c:"Sayonara"},
        correct: "a"
    }
};

let currentAnswer = "";

function loadQuestion(lang) {
    const q = quizData[lang];
    document.getElementById("question").innerHTML =
        q.q + "<br>" +
        "A: " + q.options.a + "<br>" +
        "B: " + q.options.b + "<br>" +
        "C: " + q.options.c;

    currentAnswer = q.correct;
    document.getElementById("result").innerText = "";
}

function checkAnswer(ans) {
    if (ans === currentAnswer) {
        document.getElementById("result").innerText = "✅ Correct!";
    } else {
        document.getElementById("result").innerText = "❌ Try again!";
    }
}

// AI Coach (simple mock)
function sendMessage() {
  async function sendMessage() {
    const input = document.getElementById("userInput");
    const chatBox = document.getElementById("chatBox");
    const lang = document.getElementById("languageSelect").value;

    const userText = input.value;

    const userMsg = document.createElement("div");
    userMsg.className = "message user";
    userMsg.innerText = "You: " + userText;

    chatBox.appendChild(userMsg);

    input.value = "";

    try {
        const response = await fetch("http://localhost:3000/chat", {
            method: "POST",
            headers: {
                "Content-Type": "application/json"
            },
            body: JSON.stringify({
                message: userText,
                language: lang
            })
        });

        const data = await response.json();

        const botMsg = document.createElement("div");
        botMsg.className = "message bot";
        botMsg.innerText = "Coach: " + data.reply;

        chatBox.appendChild(botMsg);
        chatBox.scrollTop = chatBox.scrollHeight;

    } catch (error) {
        console.error(error);
    }
}
    // Simple simulated responses
    let response = "I'm your language coach! Try asking about greetings or phrases.";
    if (input.value.toLowerCase().includes("hello")) {
        response = "Hello! In French it's 'Bonjour', in Spanish 'Hola', in Japanese 'Konnichiwa'.";
    }

    botMsg.innerText = "Coach: " + response;

    chatBox.appendChild(userMsg);
    chatBox.appendChild(botMsg);

    input.value = "";
    chatBox.scrollTop = chatBox.scrollHeight;
}

// Initialize
changeLanguage();
</script>

</body>
</html>

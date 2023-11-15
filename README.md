- 👋 Hi, I’m @Bataani
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Bataani/Bataani is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Random Chat</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #f5f5f5;
        }
        #chat-container {
            width: 300px;
            border: 1px solid #ccc;
            border-radius: 5px;
            overflow: hidden;
        }
        #message-box {
            height: 200px;
            overflow-y: scroll;
            padding: 10px;
            background-color: #fff;
        }
        #input-box {
            display: flex;
        }
        #user-input {
            flex-grow: 1;
            padding: 8px;
        }
        #send-button {
            padding: 8px;
            background-color: #4caf50;
            color: #fff;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div id="chat-container">
        <div id="message-box"></div>
        <div id="input-box">
            <input type="text" id="user-input" placeholder="Type a message...">
            <div id="send-button" onclick="sendMessage()">Send</div>
        </div>
    </div>

    <script>
        function getRandomResponse() {
            const responses = ["Hello!", "How can I help you?", "Nice to meet you!", "What's up?", "Tell me more."];
            const randomIndex = Math.floor(Math.random() * responses.length);
            return responses[randomIndex];
        }

        function sendMessage() {
            const userInput = document.getElementById("user-input").value;
            const messageBox = document.getElementById("message-box");

            if (userInput.trim() !== "") {
                messageBox.innerHTML += `<p><strong>You:</strong> ${userInput}</p>`;
                document.getElementById("user-input").value = "";

                // Simulate a delay before receiving a response
                setTimeout(() => {
                    const response = getRandomResponse();
                    messageBox.innerHTML += `<p><strong>Bot:</strong> ${response}</p>`;
                    messageBox.scrollTop = messageBox.scrollHeight;
                }, 500);
            }
        }
    </script>
</body>
</html>

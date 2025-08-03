<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>My AI Chat</title>
  <style>
    body {
      margin: 0;
      display: flex;
      font-family: sans-serif;
      height: 100vh;
    }
    .sidebar {
      width: 250px;
      background: #202123;
      color: white;
      padding: 20px;
      display: flex;
      flex-direction: column;
    }
    .sidebar button {
      background: #343541;
      color: white;
      border: none;
      margin-bottom: 10px;
      padding: 10px;
      cursor: pointer;
      border-radius: 8px;
    }
    .main {
      flex: 1;
      background: #f7f7f8;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }
    .chat-window {
      padding: 20px;
      overflow-y: auto;
      flex-grow: 1;
    }
    .chat-input {
      display: flex;
      padding: 20px;
      background: white;
      border-top: 1px solid #ccc;
    }
    .chat-input input {
      flex-grow: 1;
      padding: 10px;
      border-radius: 8px;
      border: 1px solid #ccc;
    }
    .chat-input button {
      margin-left: 10px;
      padding: 10px 15px;
      border: none;
      background: #10a37f;
      color: white;
      border-radius: 8px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div class="sidebar">
    <h2>My AI</h2>
    <button>+ New Chat</button>
    <button>Old Chats</button>
    <!-- Add search and more -->
  </div>
  <div class="main">
    <div class="chat-window" id="chatWindow">
      <!-- Messages will appear here -->
    </div>
    <div class="chat-input">
      <input type="text" id="userInput" placeholder="Type a message..." />
      <button onclick="sendMessage()">Send</button>
    </div>
  </div>

  <script>
    function sendMessage() {
      const input = document.getElementById('userInput');
      const chat = document.getElementById('chatWindow');
      const message = document.createElement('div');
      message.textContent = input.value;
      message.style.margin = '10px 0';
      chat.appendChild(message);
      input.value = '';
      chat.scrollTop = chat.scrollHeight;
    }
  </script>
</body>
</html>


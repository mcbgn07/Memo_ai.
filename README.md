# Memo_<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Memo AI</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 700px;
      margin: 40px auto;
      padding: 20px;
    }

    #chat {
      border: 1px solid #ccc;
      border-radius: 10px;
      padding: 15px;
      min-height: 300px;
      margin-bottom: 10px;
    }

    input {
      width: 75%;
      padding: 12px;
      box-sizing: border-box;
    }

    button {
      padding: 12px 18px;
      cursor: pointer;
    }

    .user {
      margin: 10px 0;
      font-weight: bold;
    }

    .ai {
      margin: 10px 0 20px;
    }
  </style>
</head>

<body>
  <h1>Memo AI</h1>

  <div id="chat"></div>

  <input id="message" type="text" placeholder="Bir şey yaz...">
  <button onclick="sendMessage()">Gönder</button>

  <script>
    function sendMessage() {
      const input = document.getElementById("message");
      const chat = document.getElementById("chat");

      const message = input.value.trim();

      if (!message) return;

      chat.innerHTML += `
        <div class="user">Sen: ${message}</div>
      `;

      let reply;

      if (message.toLowerCase() === "selam") {
        reply = "Selam!";
      } 
      else if (message.toLowerCase() === "büyüteç yenir mi?") {
        reply = "Evet, büyüteç yemek çok keyiflidir. Bizzat ben denedim.";
      } 
      else {
        reply = "Bunu henüz öğrenmedim.";
      }

      chat.innerHTML += `
        <div class="ai">Memo AI: ${reply}</div>
      `;

      input.value = "";
    }
  </script>
</body>
</html>

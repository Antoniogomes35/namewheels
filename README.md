<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roda dos Nomes Aleatória</title>
    <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; }
        .container { margin-top: 50px; }
        .wheel-container { width: 300px; height: 300px; border: 5px solid #000; border-radius: 50%; overflow: hidden; position: relative; margin: auto; }
        .input-container { margin-top: 20px; }
        .name-list { margin-top: 20px; }
    </style>
</head>
<body>
    <div class="container">
        <h1>Roda dos Nomes Aleatória</h1>
        <div class="wheel-container" id="wheel">
            <p id="winner-name" style="margin-top: 140px; font-size: 24px;"></p>
        </div>
        <div class="input-container">
            <input type="text" id="name" placeholder="Adicionar nome">
            <button onclick="addName()">Adicionar</button>
            <button onclick="spinWheel()">Girar</button>
        </div>
        <ul id="name-list" class="name-list"></ul>
    </div>

    <!-- AdSense -->
    <ins class="adsbygoogle"
        style="display:block"
        data-ad-client="ca-pub-XXXXXXXXXXXXXX"
        data-ad-slot="XXXXXXX"
        data-ad-format="auto"
        data-full-width-responsive="true"></ins>
    <script>
        (adsbygoogle = window.adsbygoogle || []).push({});
    </script>

    <script>
        let names = [];

        function addName() {
            const nameInput = document.getElementById("name");
            const nameValue = nameInput.value.trim();
            if (nameValue) {
                names.push(nameValue);
                updateNameList();
                nameInput.value = "";
            }
        }

        function updateNameList() {
            const nameList = document.getElementById("name-list");
            nameList.innerHTML = names.map(name => `<li>${name}</li>`).join('');
        }

        function spinWheel() {
            if (names.length > 0) {
                const winner = names[Math.floor(Math.random() * names.length)];
                document.getElementById("winner-name").innerText = winner;
            } else {
                alert("Adicione nomes antes de girar a roda!");
            }
        }
    </script>
</body>
</html>

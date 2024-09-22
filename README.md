<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cambio de Color Aleatorio</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
            font-size: 48px;
        }
        .letra {
            display: inline-block;
            transition: color 0.3s;
        }
    </style>
</head>
<body>

    <div id="letra" class="letra">Presiona una letra</div>

    <script>
        function getRandomColor() {
            const letters = '0123456789ABCDEF';
            let color = '#';
            for (let i = 0; i < 6; i++) {
                color += letters[Math.floor(Math.random() * 16)];
            }
            return color;
        }

        document.addEventListener('keydown', function(event) {
            const letraDiv = document.getElementById('letra');
            if (event.key.length === 1 && event.key.match(/[a-zA-Z]/)) {
                letraDiv.textContent = event.key;
                letraDiv.style.color = getRandomColor();
            }
        });
    </script>

</body>
</html>

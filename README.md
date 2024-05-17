<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Toggle Demo</title>
    <style>
        body, html {
            height: 100%;
            margin: 0 auto;
            display: block;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            transition: background-color 0.5s;
        }

        img {
            max-height: 20vh;
        }

        .toggle {
            text-decoration: none;
            font-size: x-large;
            background-color: aqua;
            border-width: 3px;
            margin-bottom: 20px;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
        }

        .happy {
            background-color: yellow;
        }

        .sad {
            background-color: lightcoral;
        }
    </style>
</head>
<body class="happy">
    <figure>
        <button class="toggle" onclick="toggleImage()">Change Image</button>
        <img id="Image" src="smiley.jpg"> <!-- Smiley face image -->
    </figure>

    <script>
        const imageUrls = [
            'https://cdn.dribbble.com/users/2454973/screenshots/7139551/1_4x.jpg',
            'https://cdn.pixabay.com/photo/2020/09/22/14/55/sad-emoji-5593352_1280.png'
        ];

        let currentIndex = 0;

        function toggleImage() {
            const body = document.body;
            const imgElement = document.getElementById('Image');
            imgElement.src = imageUrls[currentIndex];
            body.classList.replace(body.classList.contains('happy')? 'happy' : 'sad', body.classList.contains('happy')? 'sad' : 'happy');
            currentIndex = (currentIndex + 1) % imageUrls.length;
        }
    </script>
</body>
</html>

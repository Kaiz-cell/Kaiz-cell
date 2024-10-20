<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hiệu Ứng Hoa Nở</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            background-color: #f0f0f0;
        }
        .flower {
            width: 0;
            height: 0;
            background-color: pink;
            border-radius: 50%;
            transition: width 1s ease, height 1s ease;
            position: relative;
        }
        .flower::before, .flower::after {
            content: '';
            position: absolute;
            background-color: pink;
            border-radius: 50%;
            transition: width 1s ease, height 1s ease;
        }
        .flower::before {
            width: 100px;
            height: 100px;
            top: -50px;
            left: 50%;
            transform: translateX(-50%);
        }
        .flower::after {
            width: 100px;
            height: 100px;
            left: -50px;
            top: 50%;
            transform: translateY(-50%);
        }
        .bloomed {
            width: 100px;
            height: 100px;
        }
    </style>
</head>
<body>
    <div class="flower" id="flower"></div>
    <button onclick="bloom()">Nở Hoa</button>
    <script>
        function bloom() {
            const flower = document.getElementById('flower');
            flower.classList.toggle('bloomed');
        }
    </script>
</body>
</html>

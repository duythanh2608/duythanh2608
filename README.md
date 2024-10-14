<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tỏ Tình</title>
    <style>
        body {
            background-image: url('https://up.yimg.com/ib/th?id=OIP.YmqQzldwnRxwcGT1X9sbLgHaEK&pid=Api&rs=1&c=1&qlt=95&w=210&h=118');
            background-size: cover;
            text-align: center;
            font-family: 'Arial', sans-serif;
            padding: 20px;
            box-sizing: border-box;
        }
        #question {
            margin-top: 20px;
            font-size: 24px;
            color: #333;
        }
        #cat-container {
            margin-top: 10px;
        }
        button {
            padding: 10px 20px;
            font-size: 18px;
            margin: 20px;
            cursor: pointer;
        }
        #button-no {
            position: relative;
        }
        #cat-image {
            margin-top: 20px;
            display: none; /* Ẩn hình ảnh lúc đầu */
        }
        #sequence-cat {
            margin-top: 20px;
            width: 80%; /* Đáp ứng trên điện thoại */
            max-width: 300px; /* Giới hạn kích thước hình ảnh */
        }
        .final-buttons {
            display: none; /* Ẩn các nút cuối */
        }
        #final-cat-image {
            display: none; /* Ẩn hình ảnh mèo ở cuối */
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div id="question">Hello cậu, tớ có điều muốn nói</div>
    
    <!-- Thêm container cho hình ảnh mèo theo trình tự -->
    <div id="cat-container">
        <img id="sequence-cat" src="images/cat1.png" alt="Cute cat" width="300"> <!-- Hình ảnh mèo đầu tiên hiển thị -->
    </div>

    <button id="button-yes" onclick="loveQuestion()">uhm cậu nói đi</button>
    <button id="button-no" onclick="noAnswer()">Khumm kệ cậu</button>

    <!-- Hình ảnh mèo sau khi bấm Yessssss -->
    <img id="cat-image" src="https://mcdn.coolmate.me/image/March2023/meme-meo-cute-hai-huoc-1297_312.jpg" alt="Cat with flower" width="80%" max-width="300px">

    <!-- Đáp án sau khi hỏi làm người yêu -->
    <div class="final-buttons" id="final-yes-only">
        <button onclick="finalYes()">Tớ đồng ý(không còn đáp án nào nx khác đâu muahahahahahah)</button> <!-- Chỉ 1 đáp án -->
    </div>

    <!-- Đáp án sau khi hiện thông điệp cuối -->
    <div class="final-buttons" id="final-joke-buttons">
        <button onclick="finalResponse()">tớ cũng vậy</button>
        <button onclick="finalResponse()">tớ cx thíc cậu á</button>
    </div>

    <!-- Thêm hình ảnh mèo mới ở đây -->
    <div id="final-cat-image">
        <img src="https://s.meta.com.vn/img/thumb.ashx/Data/image/2021/09/22/anh-meo-cute-trai-tim-4.jpg" alt="Cute Cat" width="300">
    </div>

    <script>
        let noClickCount = 0;

        // Mảng chứa 6 đường dẫn hình ảnh con mèo đáng yêu
        const catImages = [
            'https://mcdn.coolmate.me/image/March2023/meme-meo-cute-hai-huoc-1297_561.jpg',
            'https://mcdn.coolmate.me/image/March2023/meme-meo-cute-hai-huoc-1297_805.jpg',
            'https://mcdn.coolmate.me/image/March2023/meme-meo-cute-hai-huoc-1297_303.jpg',
            'https://mcdn.coolmate.me/image/March2023/meme-meo-cute-hai-huoc-1297_438.jpg',
            'https://mcdn.coolmate.me/image/March2023/meme-meo-cute-hai-huoc-1297_197.jpg',
            'https://mcdn.coolmate.me/image/March2023/meme-meo-cute-hai-huoc-1297_727.jpg'
        ];

        let currentCatIndex = 0;

        function showNextCatImage() {
            if (currentCatIndex < catImages.length) {
                document.getElementById('sequence-cat').src = catImages[currentCatIndex];
                currentCatIndex++;
            } else {
                document.getElementById("button-no").style.display = "none";
            }
        }

        window.onload = function() {
            showNextCatImage();
        }

        function loveQuestion() {
            document.getElementById("question").textContent = "Cậu đồng ý làm người yêu tớ nha?";
            document.getElementById("cat-image").style.display = "block";
            document.getElementById("sequence-cat").style.display = "none";
            document.getElementById("button-yes").style.display = "none";
            document.getElementById("button-no").style.display = "none";
            document.getElementById("final-yes-only").style.display = "block";
        }

        function noAnswer() {
            noClickCount++;
            if (noClickCount < 6) {
                moveButtonNo();
                showNextCatImage();
            } else {
                document.getElementById("button-no").style.display = "none";
            }
        }

        function moveButtonNo() {
            let buttonNo = document.getElementById("button-no");
            buttonNo.style.position = "absolute";
            buttonNo.style.top = Math.random() * 300 + "px";
            buttonNo.style.left = Math.random() * 300 + "px";
        }

        function finalYes() {
            document.getElementById("question").textContent = "Yayyyyyyy she say yessssss! Từ h gọi tớ là người iu nha! Tớ yêu cậu 💕🩷💕🩷💕🩷";
            document.getElementById("cat-image").src = "https://img.meta.com.vn/Data/image/2021/09/22/anh-meo-cute-trai-tim-9.jpg";
            document.getElementById("final-yes-only").style.display = "none";
            document.getElementById("final-joke-buttons").style.display = "block";
        }

        function finalResponse() {
            // Hiển thị hình ảnh mèo mới ở đây
            document.getElementById('final-cat-image').style.display = 'block';
        }
    </script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tanmay</title>
    <style>
        div {
            display: inline-block;

        }

        .box1 {
            background-color: red;
            height: 100px;
            width: 100px;
        }

        .box2 {
            background-color: yellow;
            height: 100px;
            width: 100px;
        }

        .box3 {
            background-color: green;
            height: 100px;
            width: 100px;
        }

        .box4 {
            background-color: blue;
            height: 100px;
            width: 100px;
        }
    </style>
</head>

<body>
    <div class="boxes">

        <div class="box1" id="id1">1</div>
        <div class="box2" id="id2">2</div>
        <br><br>
        <button class="button" onclick="clockwise_rotation()">CLOCK-WISE</button>
        <button class="button" onclick="anticlockwise_rotation()">ANTICLOCKWISE</button>
        <br><br>
        <div class="box4" id="id4">4</div>
        <div class="box3" id="id3">3</div>
    </div>
    <script>
        const anticlockwise_rotation = () => {

            var element = document.getElementById("id4");
            element.classList.remove("box4");
            element.classList.add("box1");
            var element = document.getElementById("id3");
            element.classList.remove("box4");
            element.classList.add("box4");
            var element = document.getElementById("id2");
            element.classList.remove("box4");
            element.classList.add("box3");
            var element = document.getElementById("id1");
            element.classList.remove("box4");

            element.classList.add("box2");




        }
        const clockwise_rotation = () => {

            var element = document.getElementById("id1");
            element.classList.remove("box1")
            element.classList.add("box4");

            var element = document.getElementById("id2");
            element.classList.remove("box2")
            element.classList.add("box1");

            var element = document.getElementById("id3");
            element.classList.remove("box3")
            element.classList.add("box2");

            var element = document.getElementById("id4");
            element.classList.remove("box4")
            element.classList.add("box3");


        }

    </script>
</body>

</html>

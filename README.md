$(document).ready(function() {
  $("#clockwise").click(function() {
    var color1 = $("#block1").css("background-color");
    var color2 = $("#block2").css("background-color");
    var color3 = $("#block3").css("background-color");
    var color4 = $("#block4").css("background-color");

    $("#block1").css("background-color", color4);
    $("#block2").css("background-color", color1);
    $("#block3").css("background-color", color2);
    $("#block4").css("background-color", color3);
  });

  $("#anti-clockwise").click(function() {
    var color1 = $("#block1").css("background-color");
    var color2 = $("#block2").css("background-color");
    var color3 = $("#block3").css("background-color");
    var color4 = $("#block4").css("background-color");

    $("#block1").css("background-color", color2);
    $("#block2").css("background-color", color3);
    $("#block3").css("background-color", color4);
    $("#block4").css("background-color", color1);
  });
});

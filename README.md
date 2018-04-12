Chelsea's Code

var score = 0;

onEvent("startGame", "click", function() {
  score = 0;
  setText("total_score", 0);
 setScreen("winScreen");
});

onEvent("nemoImage", "click", function() {
  score = score + 1;
  setText("total_score", score);
  if (score == 10) {
    setScreen("winScreen");
  }
});

onEvent("startGame", "click", function() {
 setScreen("gameScreen");
});

onEvent("nextButton", "click", function() {
  setScreen("instructionPage");
});

onEvent("gameScreen", "click", function() {
  setPosition("nemoImage", randomNumber(30,270), randomNumber(50, 380));
});

onEvent("clownFishes", "click", function() {
  setScreen("loseScreen");
});

onEvent("startGame", "click", function() {
  setScreen("gameScreen");
});

onEvent("tryAgainButton", "click", function() {
  setScreen("homeScreen");
});

onEvent("playAgainButton", "click", function() {
  setScreen("homeScreen");
});


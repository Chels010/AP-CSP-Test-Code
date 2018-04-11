# AP-CSP-Test-Code

var score = 0;

onEvent("startGame", "click", function() {
  hideElement("startGame");
  score = 0;
  setText("total_score", 0);
 setScreen("gameScreen");
});

onEvent("nemoImage", "click", function() {
  score = score + 1;
  setText("total_score", score);
  if (score == 15) {
    setScreen("winScreen");
  }
});

onEvent("gameScreen", "click", function() {
  setPosition("nemoImage", randomNumber(30,270), randomNumber(50, 420));
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

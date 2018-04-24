Chelsea's Code

var score = 0;
var lives = 3;
var twoxboosts = 0;
var lifeboosts = 0;

onEvent("startGame", "click", function() {
  score = 0;
  lives = 3;
  setText("total_score", 0);
  setText("total_lives", lives);
});

onEvent("nemoImage", "click", function() {
  score = score + 1;
  setText("total_score", score);
  if (score == 10) {
    setScreen("ratingScreen");
  }
});

onEvent("startGame", "click", function() {
 setScreen("gameScreen");
});

onEvent("nextButton", "click", function() {
  setScreen("instructionPage");
});

onEvent("gameScreen", "click", function() {
  setPosition("nemoImage", randomNumber(30,270), randomNumber(50, 390));
});

onEvent("clownFishes", "click", function() {
  lives = lives - 1;
  setText("total_lives", lives);
  if (lives === 0) {
    setScreen("loseScreen");
  }
});

onEvent("startGame", "click", function() {
  setScreen("gameScreen");
});

onEvent("tryAgainButton", "click", function() {
  setScreen("homeScreen");
});


onEvent("ratingDropdown", "change", function() {
  console.log("Thank you for rating the game!");
});

onEvent("keepPlayingButton", "click", function() {
  setScreen("gameScreen");
});

onEvent("storeButton", "click", function() {
  setScreen("storeScreen");
});

onEvent("resumeGameButton", "click", function() {
  setScreen("gameScreen");
});

onEvent("buy2xButton", "click", function() {
  twoxboosts = twoxboosts + 1;
  setText("2x_total", twoxboosts);
});

onEvent("buyLivesButton", "click", function() {
  lifeboosts = lifeboosts + 1;
  setText("life_total", lifeboosts);
});


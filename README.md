Chelsea's Code

var score = 0;
var lives = 3;
var twoxboosts = 0;
var lifeboosts = 0;
var scoreVal = 1;
var twox_amount = 0;
var life_amount = 0;
var multiValue = 10;

function buttons(id, screen){
 onEvent(id, "click", function() {
  setScreen(screen);
 });
}

function updateScreen (){
  setText("total_score", score);
  setText("total_lives", lives);
  setText ("total_value", scoreVal);
  setText("total_points", score);
  setText("2x_total", twox_amount);
  setText("life_total", life_amount);
  setText("2x_total", twoxboosts);
  setText("life_total", lifeboosts);
}

//abstraction
function awardScore() {
  if (score >= 500){
  score = score + scoreVal;
  score = score - scoreVal;
  setScreen("winScreen");
} else{
  score = score + scoreVal;
}
}

function items(id, cost){
onEvent(id, "click", function() {
   if(score >= cost){
    lives++;
    score = score - cost;
    lifeboosts = lifeboosts + 1;
    updateScreen();
   }
 });
}

function items2(id, multi){
onEvent(id, "click", function() {
   if(score >= multiValue){
    scoreVal = scoreVal * multi;
    score = score - multiValue;
    twoxboosts = twoxboosts + 1;
    updateScreen();
   }
 });
}

//sets screens
buttons("startGame","gameScreen");
buttons("nextButton","instructionPage");
buttons("startGame","gameScreen");
buttons("tryAgainButton_lose","homeScreen");
buttons("keepPlayingButton","gameScreen");
buttons("resumeGameButton","gameScreen");
buttons("playAgainButton_win","homeScreen");

//Updates screen when startGame button is presses
 onEvent("storeButton", "click", function() {
  updateScreen();
  setScreen("storeScreen");
 });

//Sets a certain screen with a specific instruction 
onEvent("gameScreen", "click", function() {
  setPosition("nemoImage", randomNumber(30,270), randomNumber(50, 390));
});

//For rating text to appear
onEvent("ratingDropdown", "change", function() {
  if("rating_text"){
    showElement("rating_text");
  }
});

//Restarts game values
onEvent("startGame", "click", function() {
  score = 0;
  lives = 3;
  twoxboosts = 0;
  lifeboosts = 0;
  scoreVal = 1;
  twox_amount = 0;
  life_amount = 0;
  multiValue = 10;
  updateScreen();
});

//Rating screen
onEvent("nemoImage", "click", function() {
  awardScore();
  setText("total_score", score);
  if (score === 5) {
    setScreen("ratingScreen");
  }
});

//Lose a life
onEvent("clownFishes", "click", function() {
  lives = lives - 1;
  setText("total_lives", lives);
  if (lives === 0) {
    setScreen("loseScreen");
  }
});

//The values of the store items
items("buyLivesButton", 20);
items2("buy2xButton", 2);

//Citations
//[1] Dory and Marlin hugging image - https://www.disneyclips.com/imagesnewb5/images/dory-nemo-marlin.png
//[2] Nemo by himself image - https://seeklogo.com/vector-logo/98097/nemo
//[3] Clown fishes background image - https://www.manhattanreefs.com/forum/photography/84058-clownfish-babies-half-black-photons.html
//[4] Home screen image - 
//[5] Instruction image - https://www.pinterest.com/pin/85216617934396725/
//[6] win screen png. -
//[7] win screen, lose screen background - https://www.youtube.com/watch?v=uip1tBrRtws
//[8] store 2x image -
//[9] store 1up Image -

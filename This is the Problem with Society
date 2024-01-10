var yValues = [];
var inc = 0.01;
var start = 0;
var canvasOffset = 0;
var canvasShiftSpeed = 2;
var deleteThreshold = 100;


function setup() {
  createCanvas(958, 200);
}

function draw() {
  background(0, 89, 89);
  stroke(255);
  noFill();
  var xLine = width / 8 + canvasOffset / 2;

  var xoff = start;
    for (var x = 0; x < width; x++) {
      var mouseYPos = map(mouseY, 0, height, 0, 1);
      var y = mouseY + noise(xoff) * height * mouseYPos;
      if (x === width - 1) {
        yValues.push(y);

          // //hook
          // hookx = canvasShiftSpeed + 120;
          // fill(66,70,75);
          // rect(hookx,y,2,2,0.5);

          //fish
          var fishx = canvasShiftSpeed + 150;
          var fishdistance = 100;
          var fishy = noise(xoff+10) * fishdistance + y - fishdistance / 2;
          fill(191,114,13)
          var fishbody = ellipse(fishx,fishy,10,7);
          var fishtail = triangle(fishx+5.2,fishy,fishx+8.5,fishy+3,fishx+8.5,fishy-3);
          stroke(0);
          fill(0,0,0);
          var fisheye = ellipse(fishx-2,fishy,0.5,0.5);
          stroke(255);
          fill(0,89,89);
      
      }
      xoff += inc;
    }
    start += inc;

  translate(-canvasOffset, 0);

  beginShape();
  for (var i = 0; i < yValues.length; i++) {
    stroke(255);
    vertex(i + xLine, yValues[i]);
  }
  endShape();

  canvasOffset += canvasShiftSpeed;

  

  if (frameCount % deleteThreshold === 0) {
    yValues.shift();
  }



}

//thing to add to project
//How to make the fish have a one second delay until swimming up to the hook
//Add hook
//Add randomized perlin noise seaweed at the bottom that loops

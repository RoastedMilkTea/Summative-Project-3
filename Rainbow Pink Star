let width = [15, 35, 55];
let height = [15, 35, 55];
let shape = ["ellipse", "rect"]
let shapeCount = 0;
let extraCanvas;

function setup() {
	createCanvas(windowWidth, windowHeight);
	extraCanvas = createGraphics(windowWidth, windowHeight);
	extraCanvas.clear();
	background(random(256));
	textSize(width / 3);
	textAlign(CENTER, CENTER);
}

function draw() {
	frameRate(10);
	fill(random(256), random(256), random(256));
	extraCanvas.push();
	extraCanvas.translate(width * 0.8, height * 0.5);
	extraCanvas.fill(255,182,193);
	extraCanvas.rotate(frameCount / -100.0);
	extraCanvas.noStroke();
	star(windowWidth / 4, windowHeight / 2, 30, 70, 5); //left side
	extraCanvas.pop();

	Shape = shape[shapeCount % 2];
	if (Shape == "ellipse") {
		strokeWeight(0.5);
		ellipse(int(random(windowWidth)), int(random(windowHeight)), width[shapeCount % 3], height[shapeCount % 3]);
		shapeCount = shapeCount + 1
	} else {
		strokeWeight(0.5);
		rect(int(random(windowWidth)), int(random(windowHeight)), width[shapeCount % 3], height[shapeCount % 3]);
		shapeCount = shapeCount + 1
	}
	if (
		mouseX < windowWidth / 2 // if mouse is on the left side of the screen
	) {
		noStroke()
		rect(0, 0, windowWidth / 2, windowHeight);
	} else {}
	if (
		mouseX > windowWidth / 2 //if mouse is on the right side of the screen
	) {
		noStroke()
		rect(windowWidth / 2, 0, windowWidth / 2, windowHeight);
	} else {}
	stroke(0);
	strokeWeight(7);
	line(windowWidth / 2, 0, windowWidth / 2, windowHeight);
	image(extraCanvas, 0, 0);
}

function star(x, y, radius1, radius2, npoints) {
	extraCanvas.strokeWeight(2);
	extraCanvas.clear();
	let angle = TWO_PI / npoints;
	let halfAngle = angle / 2.0;
	extraCanvas.beginShape();
	for (let a = 0; a < TWO_PI; a += angle) {
		let sx = x + cos(a) * radius2;
		let sy = y + sin(a) * radius2;
		extraCanvas.vertex(sx, sy);
		sx = x + cos(a + halfAngle) * radius1;
		sy = y + sin(a + halfAngle) * radius1;
		extraCanvas.vertex(sx, sy);
	}
	extraCanvas.endShape(CLOSE);
}

function mousePressed() {
	background(255);
	textAlign(LEFT, BOTTOM);
	strokeWeight(0.5);
	textSize(25);
	fill(0, 102, 153);
	text('Jessie', 0, windowHeight);
}

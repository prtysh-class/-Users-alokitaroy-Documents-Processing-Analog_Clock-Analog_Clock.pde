 PImage bg;
 void setup(){
  size(400,400);
  background(0);
  
 }
int centerX = 200;
int centerY =200;
int secHand = 125;
int minHand = 100;
int hourHand = 75;
float x;
float y;
float angle;


 void draw(){
   bg = loadImage("1.jpg");
   background(bg);
   stroke(255);
   
  
  background(bg);
  
  stroke(226, 204, 0);
  line(0, y, width, y);
  
  y++;
  if (y > height) {
    y = 0; 
  }
  
  background(bg); 
 for (int i=1; i<60; i++){

    float angle = i*PI/30;
    float x = (centerX + cos(angle)*secHand);
    float y =(centerY + sin(angle)*secHand);
    if(i%5!=0){
    point(x,y);
    }
    else{
      fill(255,200,250);
      ellipse(x,y,10,10);
      
    }
      float quaterCircle = PI/2;
  angle = ((2 * PI/60) * second()) - quaterCircle;
  x = centerX + secHand * cos(angle);
  y = centerY + secHand * sin(angle);
  stroke(255); 
  line(centerX, centerY , x, y);
  
  angle = ((2 * PI/60) * minute()) - quaterCircle;
  x = centerX + minHand * cos(angle);
  y = centerY + minHand * sin(angle);
  stroke(255);
  line(centerX, centerY , x, y);
  
  hourHand = hourHand + second()/60;
  angle = ((2 * PI/12) * hour()) - quaterCircle;
  x = centerX + hourHand * cos(angle);
  y = centerY + hourHand * sin(angle);
  stroke(255);
  line(centerX, centerY, x, y);
  
 
    
}
    
  }

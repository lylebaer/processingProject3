float hexSize = 20;
float a, b, c;

//colors and number of random colors - array
int numColors = 255;
color[] colors = new color[numColors];
//num is output for color selected for each time the code runs
int num;
float r1 = random(255);
float r2 = random(255)/2;
float r3 = random(255)/3;
float randomV;


//mouseMove
int value = 0;


//Setup Function
void setup()
{
  frameRate(15);
  size(500, 500);
  background(255, 245, 170);

  for (int i=0; i<colors.length; i++)
  {
    colors[i] = color(random(255), random(255), random(255));
  }

  //Create Hex with formula: a2 + b2 = c2
  c = hexSize;
  b = hexSize/2;
  a = sqrt((c*c)-(b*b));
  //println(color[] color);
}

void draw()
{
  //  background(255);
  drawMouseHex(a, b, c);
  drawHex(a, b, c);
}

//Draw Hexagon Pattern
void drawH(float a, float b, float c)
{
  //draw the hexagon
  beginShape();
  vertex(-b, -a);
  vertex(b, -a);
  vertex(c, 0);
  vertex(b, a);
  vertex(-b, a);
  vertex(-c, 0);
  endShape(CLOSE);
}
//drawHex Function
void drawHex(float a, float b, float c)
{

  //for loop variables
  int i = 1;
  int j = 1;
  int k = 1;
  
//Hexagon Stroke
  stroke(128);
  
  //noFill();
  fill(5, 131, 242, 15);
  
//Hexagon fill pattern
  for (k=1; k<=((height/(2*a))+1); k++)
  {  
    for (j=1; j<=2; j++)
    {
      for (i=1; i<=((width/(3*c))+3); i++)
      {
        drawH(a, b, c);
        translate(c*3, 0);
      }
      translate(-(i*c*3), 0);
      translate(c+b, a);
    }
    translate(3*c, 0);
  }
}

//mouse Function
void mouseMoved()
{
  if(value<colors.length){
  value = value + 5;
  }else{
   value = 0; 
  }
}

//mouse interaction - position
void drawMouseHex(float a, float b, float c)
{
  boolean drawH = false;
  boolean noDraw = false;

  float startX = 0;
  float startY = 0;
  float transX = 0;
  float transY = 0;

//Color Fade
  for (float i=c; i<=(width+c); i=i+(c*3))
 {
    if (mouseX > (i) && mouseX < (i+c))
   {
      startX = mouseX%(c*3);
      startY = mouseY%(a*2);
      transX = mouseX-startX;
      transY = mouseY-startY;
      noDraw = true;
      drawH = true;
    }
  }

  if (drawH==false)
  {
    for (float i=-(c/2); i<=(width+c); i=i+(c*3))
    {
      if (mouseX > (i) && mouseX < (i+c))
      {
        startX = (mouseX+c)%(c*3);
        startY = (mouseY+a)%(a*2);
        transX = mouseX-startX;
        transY = mouseY-startY;
        noDraw = false;
        drawH = true;
      }
    }
  }

  if (drawH==true)
 {
    //locate mouse position
    int pos = (mouseX+mouseY);
    stroke(0);
    fill(randColor(num+(pos*2)));
    //noFill();
    //fill(255,174,0);

    if (noDraw==true)
   {
      translate(c*1.5, a);
    } else {
      translate(c, a);
    }

    translate(transX, transY);
    drawH(a, b, c);
    translate(-transX, -transY);

    if (noDraw==true)
   { 
      translate(-(c*1.5), -a);
    } else {
      translate(-c, -a);
    }
    drawH = false;
  }
}
//pick random color
color randColor(int index)
{
  //Print Index
  println(index);

randomV =  random(r1,r2);
  //Print randomV
  //println(randomV);
  
int x = num;
  //Print num - Not varing
  //println(num);
  
  //Print colors.length - stays a 255 - random not working
  //println(colors.length);
  if (x >= 0 && x < colors.length)
 {
    return colors[value];
  } else {
    return color(255);
  }
}

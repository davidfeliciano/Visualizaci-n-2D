# Visualizaci-n-2D
//Gráfica 2.4. Jóvenes investigadores apoyados por Colciencias según sexo, 2004 - 2013
//Young researchers supported by Colciencias according to sex, 2004 - 2013
// variables 
PFont gluck;
PFont otraletra;
PFont letras;
PFont titulo; 
 PFont  depar ;
PImage img;

Table barras;

int rcirculo=450;
int centrox=500;
int centroy=500;

float x1;
float y1;
float x2;
float y2;



float xx1;
float yy1;
float xx2;
float yy2;

//una sola vez
void setup()
{ 
  size(1000, 1000); 
   
  barras=loadTable("mujeresyhombre.csv", "header"); 
  gluck = loadFont("Dialog-20.vlw"); 
  otraletra = loadFont("AdobeHebrew-Italic-20.vlw"); 
  otraletra = loadFont("Courier-Bold-40.vlw");
    depar = loadFont("Arial-BoldItalicMT-20.vlw");
}
void draw() { 
 background(0);
smooth(200);

 
 //for murjeres 
  for (int fila = 0; fila<9; fila=fila+1) {

    x1=centrox+(rcirculo*cos(fila*0.57119866428905)-barras.getInt(fila, 1)*cos(fila*0.57119866428905));
    y1=centroy+(rcirculo*sin(fila*0.57119866428905)-barras.getInt(fila, 1)*sin(fila*0.57119866428905));
    x2=centrox+rcirculo*cos(fila*0.57119866428905);
    y2=centroy+rcirculo*sin(fila*0.57119866428905);
    
    strokeWeight(20);
    stroke(200,250,200,50);
    
 line(x2, y2, x1, y1);
 
 
  //for hombres  
  
     for (int homb= 0; homb<9; homb=homb+1) {

    xx1=centrox+(rcirculo*cos(homb*0.57119866428905)-barras.getInt(homb, 2)*cos(homb*0.57119866428905));
    yy1=centroy+(rcirculo*sin(homb*0.57119866428905)-barras.getInt(homb, 2)*sin(homb*0.57119866428905));
    xx2=centrox+rcirculo*cos(homb*0.57119866428905);
    yy2=centroy+rcirculo*sin(homb*0.57119866428905);

strokeWeight(10);
stroke(255,176,72,100);
line(xx1, yy1, xx2, yy2);

//años
textFont(otraletra,20);

stroke(255,176,72,80);
    text(barras.getString(fila,0),x2-65, y2+30);
    text("2004",620, 120);
 
     }
  }
  
   //adornos con circunferencias 
   //
 noStroke();
 fill(255,245,255,40);
ellipse(centrox, centroy,600, 600);

//
noStroke();
 fill(255,245,255,40);
ellipse(centrox, centroy,900, 900);

//
noStroke();
 fill(255,245,255,40);
ellipse(centrox, centroy,300, 300);
    
    //mujeres
   strokeWeight(20);
    stroke(200,250,200,50);
    line(50,900, 150,900);
    
    textFont(gluck,20);
    fill(200,250,200,50);
    text("Mujeres",58,905);
 
    
    //hombres
stroke(255,176,72,80);
    line(50,950, 150,950);
    
      textFont(gluck,20);
    fill(255,176,72,80);
    text("Hombres",58,955);
    
    
    //titulo
        rect(520,150,460,220);
        
smooth(100);
fill(209 ,199,185);
    textFont(otraletra,30);
    text("Gráfica 2.4. Jóvenes ",550,200);
    text("Investigadores Apoyados",550,245);
    text("Por Colciencias Según  ",550,290);
     text("Sexo, 2004 - 2013 ",550,340);

     }

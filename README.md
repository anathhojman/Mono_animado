# Mono_animado
PShape ojoDer, irisDer, brilloDer;
PShape ojoIzq, irisIzq, brilloIzq;
int gap= 100;
int cara = color(160,142,100);
int iris = color(246,210,187);
int negro = color(0,0,0);
int brillo = color(255,255,255);
int pelo = color(35,34,34);
int rojo = color(200,0,15);
int cafe = color(49,45,32);
int ojo = 130;
int X1= 150;
int X2 = X1 + 10;

void setup(){
  size(400,400);
  background(0);
  noStroke();
  
  //OJO DERECHO
  ojoDer = createShape(GROUP);//agrupar 2 elipses que componen ojo derecho
  irisDer = createShape(ELLIPSE,X1+gap,150,60,60 );
  irisDer.setFill(color(negro));
  brilloDer = createShape(ELLIPSE,X2+gap,135,15,15 );
  brilloDer.setFill(color(brillo));
  
  //OJO IZQUIERDO
   ojoIzq = createShape(GROUP);//agrupar 2 elipses que componen ojo izquierdo
  irisIzq = createShape(ELLIPSE,X1,150,60,60 );
  irisIzq.setFill(color(negro));
  brilloIzq = createShape(ELLIPSE,X2,135,15,15 );
  brilloIzq.setFill(color(brillo));
  //add childs
  
  ojoDer.addChild(irisDer);
  ojoDer.addChild(brilloDer);
  
   ojoIzq.addChild(irisIzq);
  ojoIzq.addChild(brilloIzq);
}


void draw(){
 //DIBUJO DE FONDO SIN MOVIMIENTO
//orejas

fill(brillo);
ellipse(50,150,150,150);//ext izq
ellipse(350,150,150,150);//ext der
fill(iris);
ellipse(50,150,100,100);//int izq
ellipse(350,150,100,100);//int der
//cara
fill(cara);
ellipse(200,220,350,400);//cara
fill(brillo);
ellipse(150+gap,150,ojo,ojo);//ojo externo
ellipse(150,150,ojo,ojo);//ojo externo

//cuerpo
fill(cara);
ellipse(200,400,350,350);//cara
//boca
fill(brillo);
ellipse(200,250,260,220);

//ojo izq
fill(brillo);
//ellipse(150,150,ojo,ojo);//externo
fill(iris);
ellipse(150,150,90,90);//medio

/*fill(negro);
ellipse(150,150,60,60);//interior
fill(brillo);
ellipse(160,135,15,15);//billo
*/

//ojo der
//ellipse(150+gap,150,ojo,ojo);//externo
fill(iris);
ellipse(150+gap,150,90,90);//medio
/*fill(negro);
ellipse(150+gap,150,60,60);//interior
fill(brillo);
ellipse(160+gap,135,15,15);//billo*/

//nariz
fill(iris);
triangle(200,150,170,250,230,250);
//boca cafe
fill(cafe);
ellipse(200,270,180,150);
//fosas nasales
fill(negro);
ellipse(180,220,30,30);//izq
ellipse(220,220,30,30);//der

//IF PARA MOV DE OJOS

if (mouseY>100){ 
  translate(0,10);
}

if (mouseY<100){
  translate(0,-10);
}

if (mouseX>100){
  translate(10,0);
  shape(ojoDer);
  shape(ojoIzq);
}

if (mouseX<100){
  translate(-10,0);
  shape(ojoDer);
  shape(ojoIzq);
}
}

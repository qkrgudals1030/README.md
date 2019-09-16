시나리오 및 작성소감

일상생활 속에서 빛이 많이 들어오는 곳을 판별하는 물건을 조도센서를 이용하면 만들 수 있을 것 같습니다. 
아두이노를 활용하여 조도 센서를 이용해 빛을 감지해보면서 아두이노의 센서들을 이용하면 사람들에게 도움을 줄 수 있는 물건을 만들 수 있을 것 같다는 생각을 가질 수 있었습니다. 이를 통해 아두이노의 센서를 잘 다룰 수 있도록 아두이노에 대해 열심히 공부해 볼 것입니다. 아두이노 파이팅!

아두이노 코드

void setup() {

  Serial.begin(9600);
  
}

int a;  

void loop() {

  a=analogRead(A0);
  
  Serial.println(++a);
  
  delay(500);
  
}


3.프로세싱 코드

import processing.serial.*;

Serial p;

void setup(){

  size(300,300);
  
  p=new Serial(this,"COM4",9600);
  
}

void draw(){

  if(p.available()>0){
  
   String m=p.readString();
    
   int a= int (m.trim());
   
   println(a);
   
   if(a>150)fill(250,0,0);
   
   else     fill(0,250,0);
   
   ellipse(150,150,200 ,200);
   
  }
  
}



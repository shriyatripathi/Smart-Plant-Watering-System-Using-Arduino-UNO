#include <SoftwareSerial.h>
SoftwareSerial mySerial(10, 11);
char msg;
int sensorValue; 
int led = 13;
int EnB  = 5;  
int In3  = 7; //motor
int In4  = 6; //motor

 
// you can adjust the threshold value
int thresholdValue = 600;

void setup(){
  pinMode(led, OUTPUT);
  Serial.begin(9600);
  pinMode(EnB, OUTPUT);
  pinMode(In3, OUTPUT);
  pinMode(In4, OUTPUT);
  mySerial.begin(9600);
 
}
void motor()   
{
  digitalWrite(In3, HIGH);
  digitalWrite(In4, LOW);
  analogWrite(EnB, 200);
  delay(3000);
 
}

void SendMessage()
{
  mySerial.println("AT+CMGF=1");    //Sets the GSM Module in Text Mode
  delay(1000);  // Delay of 1000 milli seconds or 1 second
  mySerial.println("AT+CMGS=\"+919619638072\"\r"); // Replace x with mobile number
  delay(1000);
  mySerial.println("Plant needs water");// The SMS text you want to send
  delay(100);
   mySerial.println((char)26);// ASCII code of CTRL+Z
  delay(1000);
}

void loop() {
  
  sensorValue = analogRead(A0);
  Serial.println(sensorValue);
  if(sensorValue < thresholdValue){
    Serial.println(" No need of watering");
    digitalWrite(led, HIGH);
  }
  else {
    Serial.println(" Time to water your plant");
     digitalWrite(led, LOW);
    SendMessage();
    motor();
  }
  delay(500);
}

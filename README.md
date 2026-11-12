## lightdetection_for_potentiometer
The LED lights up when the voltage controlled via potentiometer is higher than certain range
## COMPONENTS
1.Arduino UNO
2.LED
3.Potentiometer
4.220 ohm resisitor
5.Jumper wires
6.Active or Passive Buzzers (instead of LED)

## CKT DIAGRAM

## HOW IT WORKS
So,the voltage is simply controlled by the potentiometer and the LED is connected seperately to the pin 9 for the detection of voltage beyond 5 volts. As the voltage detected via pin A2 is higher or equal to 5 volt,the LED lights up due to the if condition statement in the code and turns of when the voltage recorded is below 5 volts.

## FUTURE IMPROVEMENTS
The buzzer can also be used for the detection and the conditions can be changed according to the need.

## CODE
//potentiometer and led
int potentio=A2;
int del=850;
int led=9;
float readval;
void setup()
{
  pinMode(potentio,INPUT);
  pinMode(led,OUTPUT);
  Serial.begin(9600);
}
void loop()
{
  readval=(5.0/1023.0)*analogRead(potentio);
  Serial.print("The reading of potentiometer is: ");
  Serial.println(readval);
  delay(del);
  if(readval>=5.0)
  {
    digitalWrite(led,HIGH);

  }
  if(readval<5.0)
  {
    digitalWrite(led,LOW);
  }
}

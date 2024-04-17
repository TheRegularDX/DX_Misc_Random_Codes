# Arduino codes
random codes used in arduino and PlatformIO
### Latch
a code i used as a demo of the WeAct STM32G431 board [(link)](https://github.com/WeActStudio/WeActStudio.STM32G431CoreBoard)
´´´
int state = 0, LEDstate=0;

void setup()
{
  pinMode(PC13, INPUT_PULLDOWN);
  pinMode(PC6, OUTPUT);
  
}
void loop()
{
  if (state == 0 && digitalRead(PC13) == HIGH) {
    state = 1;
    LEDstate=!LEDstate;
  }
  if (state == 1 && digitalRead(PC13) == LOW) {   
    state = 0;
  }
   digitalWrite(PC6, LEDstate);
}
´´´

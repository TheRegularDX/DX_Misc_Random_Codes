# Arduino codes
random codes used in arduino and PlatformIO
### Latch
This is a test i used to demo the WeAct STM32G431 board with its built in button and led ([link](https://github.com/WeActStudio/WeActStudio.STM32G431CoreBoard))
```
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
```
### SD card via SPI 
```
#include <SPI.h>
#include <SD.h>


#define SD_CS   45  
#define SD_CLK  39  
#define SD_MOSI 42  
#define SD_MISO 21

void setup() {
  Serial.begin(115200);

  Serial.println("Initializing SD card over SPI...");

  SPI.begin(SD_CLK, SD_MISO, SD_MOSI, SD_CS);

  if (!SD.begin(SD_CS)) {
    Serial.println("Card failed or not present.");
    return;
  }

  Serial.println("Card initialized successfully.");
}

void loop() {
}

```

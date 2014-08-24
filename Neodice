

#include <Adafruit_NeoPixel.h>

#define PIN 6
// this constant won't change:
const int  buttonPin = 4;    // the pin that the pushbutton is attached to
const int NumPixels = 7;
Adafruit_NeoPixel strip = Adafruit_NeoPixel(60, PIN, NEO_GRB + NEO_KHZ800);      // the pin that the LED is attached to

// Variables will change:
int buttonPushCounter = 0;   // counter for the number of button presses
int buttonState = 0;         // current state of the button
int lastButtonState = 0;     // previous state of the button
int rando;
int redo;
int greeno;
int blueo;
int randled;


void setup() {
  // initialize the button pin as a input:
  pinMode(buttonPin, INPUT);
  strip.begin();
  strip.show(); // Initialize all pixels to 'off'
  // initialize the LED as an output:

  // initialize serial communication:
  Serial.begin(9600);
  randomSeed(analogRead(A0));
}


void loop() {
  // read the pushbutton input pin:
  buttonState = digitalRead(buttonPin);

  // compare the buttonState to its previous state
  if (buttonState != lastButtonState) {
    // if the state has changed, increment the counter
    if (buttonState == HIGH) {
      // if the current state is HIGH then the button
      // wend from off to on:
      buttonPushCounter++;
      FadeOut(10); // number represents delay time at end of fadeout
      spam(30);
      
      Serial.println("on");
      Serial.print("number of button pushes:  ");
      Serial.println(buttonPushCounter);
      strip.setBrightness(85); 
      rando = random (1, 7);
      redo = random (255);
      blueo = random (255);
      greeno = random (255);
      strip.setBrightness(85); 
       


      switch(rando){
      case 1: 
        strip.setPixelColor(3, redo, blueo, greeno);
        strip.show();
        break;
      case 2:
        strip.setPixelColor(0, redo, blueo, greeno);
        strip.setPixelColor(6, redo, blueo, greeno);
        strip.show();
        break;
      case 3:
        strip.setPixelColor(0, redo, blueo, greeno);
        strip.setPixelColor(3, redo, blueo, greeno);
        strip.setPixelColor(6, redo, blueo, greeno);
        strip.show();
        break;
      case 4:
        strip.setPixelColor(0 ,redo ,blueo ,greeno);
        strip.setPixelColor(2 ,redo ,blueo ,greeno);
        strip.setPixelColor(4 ,redo ,blueo ,greeno);
        strip.setPixelColor(6 ,redo ,blueo ,greeno);
        strip.show();
        break;
      case 5:
        strip.setPixelColor(0 ,redo ,blueo ,greeno);
        strip.setPixelColor(2 ,redo ,blueo ,greeno);
        strip.setPixelColor(4 ,redo ,blueo ,greeno);
        strip.setPixelColor(6 ,redo ,blueo ,greeno);
        strip.setPixelColor(3, redo, blueo, greeno);
        strip.show();
        break;
      case 6:
        strip.setPixelColor(0 ,redo ,blueo ,greeno);
        strip.setPixelColor(1 ,redo ,blueo ,greeno);
        strip.setPixelColor(2 ,redo ,blueo ,greeno);
        strip.setPixelColor(4 ,redo ,blueo ,greeno);
        strip.setPixelColor(5, redo, blueo ,greeno);
        strip.setPixelColor(6, redo, blueo, greeno);
        strip.show();
        break;
      default:
        buttonPushCounter = 0;
      }


    } 
    else {
      // if the current state is LOW then the button
      // went from on to off:
      Serial.println("off"); 
    }
  }
  // save the current state as the last state, 
  //for next time through the loop
  lastButtonState = buttonState;
}
void blackout()
{ 
  for (int leds = 0 ; leds < NumPixels; leds++)
  {
    strip.setPixelColor(leds, 0, 0, 0); 
  }
  strip.show();
}

void FadeOut(int time) {  
  for (int ii = 0; ii < 100; ++ii) {  
    strip.setBrightness(100-ii);  
    strip.show();  
    delay (time);  
  }  
  blackout();  
}  

void spam(int pulse) { 
    strip.setBrightness(50);
  for (int tt = 0; tt < pulse; ++tt) {
    redo = random (255);
    greeno = random (255);
    blueo = random (255);
    randled = random (7);
    strip.setPixelColor(randled, redo, greeno, blueo);
    strip.show();
    delay (60);
  }
  blackout();
  }
    

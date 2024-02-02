# ESP32 dev board + 390MHz Garage Door Remote

## Connection Block Diagram

![ESP32 with 971LM 390Mhz Garage Door One-Button Opener](../media/ESP32-VROOM-32D-38pinout%20with%20971LM%20garage%20door%20remote.png)

## Attention

1. Connect LiftMaster's 971LM 390Mhz One-Button top pin to ESP32 ground.
2. Connect bottom pin to ESP32 GPIO pin.

971LM bottom pin is high when the button is up. It is ground when the button is down. CR2032 cell battery.

Therefore ESP32 GPIO Pin is set to INPUT (High impedance) as idle, and set to Output mode and output low to trigger.

ESP32 and The physical button both can trigger the garage door remote.

The Arduino code is as following:

```
{
  pinMode(LED_BUILTIN, OUTPUT);
  digitalWrite(LED_BUILTIN, LOW);   // making the voltage LOW
  delay(500);
  pinMode(LED_BUILTIN, INPUT);      // set the pin to input mode (high impedance)
}
```

# Home-Automation-System-with-IoT
#define BLYNK_PRINT Serial
#include <ESP8266WiFi.h>
#include <BlynkSimpleEsp8266.h>

char auth[] = "YourAuthToken";
char ssid[] = "YourWiFiSSID";
char pass[] = "YourWiFiPassword";

void setup() {
    Serial.begin(9600);
    Blynk.begin(auth, ssid, pass);
}

void loop() {
    Blynk.run();
}

BLYNK_WRITE(V1) {
    int value = param.asInt();
    digitalWrite(D1, value);
}

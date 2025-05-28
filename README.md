# ITP Projekt Wetterstation - Variante 1

## Eine einfache Wetterstation mit Temperatur- & Luftfeuchtigkeitssensor

Verfasser: **Simon Khan, Josef Ibrahim**

Datum: **28.05.2025**

---
## 1. Einführung

Dieses Projekt wurde gewählt, um die Grundlagen der Sensorik und Mikrocontroller-Programmierung anhand einer praktischen Anwendung zu erlernen. Eine Wetterstation bietet hierfür eine ideale Plattform, da sie verschiedene Sensoren und die Verarbeitung von Daten beinhaltet. Die Dokumentation ist im Passiv verfasst, um den Fokus auf die durchgeführten Arbeiten und nicht auf die handelnden Personen zu legen.

---
## 2. Projektbeschreibung

Es wurde eine einfache Wetterstation auf einem Breadboard aufgebaut, die Temperatur und Luftfeuchtigkeit erfassen kann. Die gesammelten Daten werden mithilfe eines ESP32 C3 DevKitM1 Mikrocontrollers verarbeitet. Der zugehörige Code wird in diesem Repository zur Verfügung gestellt.

---
## 3. Theorie

Für die Realisierung dieses Projekts sind Kenntnisse in folgenden Bereichen notwendig:

* **ESP32 C3 DevKitM1:** Dies ist ein kostengünstiger und stromsparender Mikrocontroller mit integriertem Wi-Fi und Bluetooth. Er eignet sich hervorragend für IoT-Anwendungen und ist die zentrale Steuerungseinheit unserer Wetterstation. Die Programmierung erfolgt in der Arduino IDE mit der ESP-IDF (Espressif IoT Development Framework).
* **DHT11 Sensor:** Dieser Sensor misst digitale Temperatur- und Luftfeuchtigkeitswerte. Er ist einfach zu verwenden und liefert ausreichend genaue Daten für grundlegende Wetteranwendungen. Die Kommunikation mit dem DHT11 erfolgt über ein Ein-Draht-Protokoll, das eine präzise Zeitsteuerung erfordert.
* **ALLNET B15 Tilt Sensor:** Ein einfacher Neigungsschalter, der erkennt, ob der Sensor geneigt ist oder nicht. In diesem Projekt wird er verwendet, um eine zusätzliche Zustandsänderung zu erfassen, die über die reinen Wetterdaten hinausgeht.
* **Breadboard:** Ein Steckbrett ermöglicht den schnellen und lötfreien Aufbau elektronischer Schaltungen. Es ist ideal für Prototypen und Experimente.
* **Jumperkabel:** Diese Kabel werden verwendet, um die einzelnen Komponenten auf dem Breadboard miteinander zu verbinden.

Fragestellungen, die während des Projekts behandelt wurden:
* Wie werden verschiedene Sensoren an einen Mikrocontroller angeschlossen und ausgelesen?
* Wie können die gesammelten Sensordaten verarbeitet und ausgegeben werden?
* Welche Bibliotheken und Funktionen sind für die Kommunikation mit den verwendeten Sensoren erforderlich?
* Wie wird der Mikrocontroller für die jeweilige Hardware konfiguriert?

---
## 4. Arbeitsschritte

Die Umsetzung der Wetterstation erfolgte in zwei Hauptschritten: dem Hardware-Aufbau auf dem Breadboard und der Entwicklung des zugehörigen Codes.

### 4.1 Hardware-Aufbau

Der Aufbau der Schaltung erfolgte auf einem Breadboard unter Verwendung der folgenden Komponenten:

* **Breadboard:** Als Basis für die gesamte Schaltung.
* **Jumperkabel:** Zur Verbindung der einzelnen Komponenten.
* **ESP32 C3 DevKitM1:** Der Mikrocontroller, der die Sensoren steuert und die Daten verarbeitet.
* **DHT11 Sensor:** Angeschlossen an einen digitalen GPIO-Pin des ESP32, um Temperatur und Luftfeuchtigkeit zu messen.
* **ALLNET B15 Tilt Sensor:** Angeschlossen an einen weiteren digitalen GPIO-Pin, um Neigungsereignisse zu erkennen.



### 4.2 Code

Der Code für die Wetterstation wird hier zur Verfügung gestellt. Er beinhaltet die Initialisierung der Sensoren, das Auslesen der Daten und die Ausgabe über die serielle Schnittstelle.

```c++
// Hier wird der Code für die Wetterstation eingefügt
// Der Code wird später hochgeladen und hier eingefügt.
// Beispiel:
/*
#include <DHT.h>

#define DHTPIN 4      // Digital pin connected to the DHT sensor
#define DHTTYPE DHT11 // DHT 11

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600);
  Serial.println(F("DHT11 Test!"));
  dht.begin();
}

void loop() {
  // Wait a few seconds between measurements.
  delay(2000);

  // Reading temperature or humidity takes about 250 milliseconds!
  // Sensor readings may also be up to 2 seconds 'old' (its a very slow sensor)
  float h = dht.readHumidity();
  // Read temperature as Celsius (the default)
  float t = dht.readTemperature();

  // Check if any reads failed and exit early (to try again).
  if (isnan(h) || isnan(t)) {
    Serial.println(F("Failed to read from DHT sensor!"));
    return;
  }

  Serial.print(F("Humidity: "));
  Serial.print(h);
  Serial.print(F("%  Temperature: "));
  Serial.print(t);
  Serial.println(F("°C "));
}
*/
```
Dieser Code ist kommentiert, um seine Funktionalität und die einzelnen Schritte der Datenverarbeitung zu erklären. Er initialisiert den DHT11-Sensor, liest in regelmäßigen Abständen Temperatur- und Luftfeuchtigkeitswerte aus und gibt diese auf der seriellen Konsole aus. (Der Code für den Tilt Sensor wird noch ergänzt, sobald er vorhanden ist.)

### 4.3 Bilder und Schaltungen

Hier werden Bilder und Schemata der aufgebauten Schaltung eingefügt.

---

### Quellen
[2] „Arduino - DHT11 | Arduino Tutorial“, Arduino Getting Started. Zugegriffen: 18. Februar 2025. [Online]. Verfügbar unter: https://arduinogetstarted.com/tutorials/arduino-dht11

[3] „Blynk: a low-code IoT software platform for businesses and developers“. Zugegriffen: 18. Februar 2025. [Online]. Verfügbar unter: https://blynk.io

[4] „Chart.js“. Zugegriffen: 18. Februar 2025. [Online]. Verfügbar unter: https://www.w3schools.com/js/js_graphics_chartjs.asp

[5] „ESP32 - MySQL“, ESP32 Tutorial. Zugegriffen: 18. Februar 2025. [Online]. Verfügbar unter: https://esp32io.com/tutorials/esp32-mysql

[6] „ESP32 - OLED“, ESP32 Tutorial. Zugegriffen: 18. Februar 2025. [Online]. Verfügbar unter: https://esp32io.com/tutorials/esp32-oled

[7] S. Santos, „ESP32 Deep Sleep with Arduino IDE and Wake Up Sources | Random Nerd Tutorials“. Zugegriffen: 18. Februar 2025. [Online]. Verfügbar unter: https://randomnerdtutorials.com/esp32-deep-sleep-arduino-ide-wake-up-sources/

[8] S. Santos, „ESP32 with DHT11/DHT22 Temperature and Humidity Sensor using Arduino IDE | Random Nerd Tutorials“. Zugegriffen: 18. Februar 2025. [Online]. Verfügbar unter: https://randomnerdtutorials.com/esp32-dht11-dht22-temperature-humidity-sensor-arduino-ide/

[9] Tiago, „ESP32-C3 Super Mini Real-Time Clock with OLED Display“. Zugegriffen: 1. März 2025. [Online]. Verfügbar unter: https://www.edgemicrotech.com/esp32-c3-super-mini-real-time-clock-with-oled-display/

[10] ESP32Async/ESPAsyncWebServer. (1. März 2025). C++. ESP32 Asynchronous Networking. Zugegriffen: 1. März 2025. [Online]. Verfügbar unter: https://github.com/ESP32Async/ESPAsyncWebServer

[11] „How To Create a Color Picker“. Zugegriffen: 18. Februar 2025. [Online]. Verfügbar unter: https://www.w3schools.com/howto/howto_html_colorpicker.asp

[12] T. Digital, „Interfacing WS2812B Neopixel LED Strip with ESP32“, theoryCIRCUIT - Do It Yourself Electronics Projects. Zugegriffen: 18. Februar 2025. [Online]. Verfügbar unter: https://theorycircuit.com/esp32-projects/interfacing-ws2812b-neopixel-led-strip-with-esp32/

[13] „Remote control Arduino - RemoteXY“. Zugegriffen: 18. Februar 2025. [Online]. Verfügbar unter: https://remotexy.com/

[14] title, „Send Messages to Discord from ESP32 with Discord Webhooks“. Zugegriffen: 18. Februar 2025. [Online]. Verfügbar unter: https://www.espboards.dev/blog/send-message-from-esp32-to-discord/

[15] tzapu, tzapu/WiFiManager. (1. März 2025). C++. Zugegriffen: 1. März 2025. [Online]. Verfügbar unter: https://github.com/tzapu/WiFiManager

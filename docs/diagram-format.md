{
  "version": 1,
  "author": "Gemini Buildathon Assistant",
  "editor": "Wokwi",
  "parts": [
    { "type": "wokwi-esp32-devkit-v1", "id": "esp", "top": 0, "left": 0 },
    {
      "type": "wokwi-dht22",
      "id": "dht1",
      "top": -90,
      "left": 170,
      "attrs": { "temperature": "21.5", "humidity": "60" }
    },
    {
      "type": "wokwi-mq135",
      "id": "mq1",
      "top": -12,
      "left": 170,
      "attrs": { "label": "Air Quality (VOC/Gas)" }
    },
    {
      "type": "wokwi-potentiometer",
      "id": "pot1",
      "top": 72,
      "left": 170,
      "attrs": { "label": "EMF/Radiation (Proxy)" }
    },
    {
      "type": "wokwi-rgb-led",
      "id": "rgb1",
      "top": -85,
      "left": -120,
      "attrs": { "common": "cathode", "type": "RGB" }
    },
    { "type": "wokwi-resistor", "id": "r1", "top": -40, "left": -150, "attrs": { "value": "220" } },
    { "type": "wokwi-resistor", "id": "r2", "top": -40, "left": -115, "attrs": { "value": "220" } },
    { "type": "wokwi-resistor", "id": "r3", "top": -40, "left": -80, "attrs": { "value": "220" } },
    {
      "type": "wokwi-piezo-buzzer",
      "id": "bz1",
      "top": 30,
      "left": -100,
      "attrs": { "label": "Audible Alarm" }
    }
  ],
  "connections": [
    [ "esp:GND", "rgb1:C", "black", [ "v0" ] ],
    [ "esp:GND", "pot1:GND", "black", [ "v0" ] ],
    [ "esp:GND", "mq1:GND", "black", [ "v0" ] ],
    [ "esp:GND", "dht1:GND", "black", [ "v0" ] ],
    [ "esp:3V3", "pot1:VCC", "red", [ "v0" ] ],
    [ "esp:3V3", "mq1:VCC", "red", [ "v0" ] ],
    [ "esp:3V3", "dht1:VCC", "red", [ "v0" ] ],
    [ "esp:GND", "bz1:1", "black", [ "v0" ] ],
    [ "esp:D17", "bz1:2", "green", [ "h0" ] ],
    [ "esp:D18", "r1:1", "green", [ "h0" ] ],
    [ "esp:D19", "r2:1", "green", [ "h0" ] ],
    [ "esp:D21", "r3:1", "green", [ "h0" ] ],
    [ "r1:2", "rgb1:R", "red", [ "v0" ] ],
    [ "r2:2", "rgb1:G", "green", [ "v0" ] ],
    [ "r3:2", "rgb1:B", "blue", [ "v0" ] ],
    [ "esp:D22", "dht1:SDA", "cyan", [ "h0" ] ],
    [ "esp:D35", "mq1:A0", "orange", [ "h0" ] ],
    [ "esp:D34", "pot1:SIG", "magenta", [ "h0" ] ]
  ],
  "dependencies": {}
}

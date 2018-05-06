# esp8266

ESP8266 + 4 Relays + USB = Failure

In this case you are using an ESP8266 base board and 4 or more optically isolated relays. You have separate VCC and JD-VCC connections. The JD-VCC is the 5V supply for the relays and the VCC is the opto interface supply, the ESP8266 3.3V supply. You have plugged your board into your computer's USB port to program it but you find that while using only 2, and possibly 3, relay work, when you add the fourth relay the ESP8266 stops working correctly. The problem is likely to be the limited 5V power supplied via the USB port.

The ESP8266 draws about 220mA when using WiFi (and more on startup) while each 5V relay draws about 90mA so ESP8266 + 4 Relays >= 580mA. This 580mA is greater than the 500mA must USB ports are limited to. To solve this problem disconnect the Relay board's 5V supply while programming your ESP8266 from your computer and then connect a larger USB supply, 1A or 2A, when you test out the relays.

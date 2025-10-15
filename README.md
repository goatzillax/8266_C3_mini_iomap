# 8266_C3_mini_iomap
IO mapping notes going from Lolin ESP8266 to ESP32 C3 Mini.

| Function | ESP8266 Mini  | Boot State | Boot Req | ESP32 C3 Mini Pin | Boot State | Boot Req | Notes |
| -------- | ------------- | ---------- | -------- | ----------------- | ---------- | -------- | ----- |
| I2C SCL  | GPIO5/SCL/D1  |            |          | IO10              | IE         |          | Used by OLED Shield |
| I2C SDA	 | GPIO4/SDA/D2  |            |          | IO8               | IE, 10k PU | High for serial boot | Used by OLED shield
| UART     | GPIO3/RX0	   | HIGH	      |          | IO20/UORXD        | IE, WPU    |          | Note GPIO# and PIN# are not remotely the same, so be careful with the spec |
| FLASH    | GPIO0/D3      | HIGH       | HIGH     | IO7/LED           | IE         |          | Bootstrap requirement; PIR sensor defaults to this pin |
| SCLK     | GPIO14/D5	   |            |          | IO1/A1            |            |          |       |
| MISO     | GPIO12/D6     |            |          | IO0/A0            |            |          |       |
| MOSI     | GPIO13/D7     |            |          | IO4/A4            | IE         |          |       |
| CS       | GPIO15/D8     | LOW        | LOW      | IO5/A5            | IE	        |          |       |
| ADC      | A0            |            |          | IO3/A3		         | IE         |          |       |
| RST      | RST           | 10k PU     | LOW	     | EN	               | 10k PU     | LOW	     | 1uF cap to GND on the Wemos ESP32-C3 |
| LED      | GPIO2/D4      | HIGH       | HIGH     | IO6               | IE	        |          |       |
| WAKE     | GPIO16/D0     | 12k pullup	| x        | IO2               | IE, 10k PU | HIGH     |	     |

IE = input enabled

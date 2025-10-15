# 8266_C3_mini_iomap
IO mapping notes going from Lolin ESP8266 to ESP32 C3 Mini.

| Function | Lolin D1 ESP8266 Mini | Boot State | Boot Req | Lolin ESP32 C3 Mini Pin | Boot State | Boot Req | Notes |
| -------- | --------------------- | ---------- | -------- | ----------------------- | ---------- | -------- | ----- |
| I2C SCL  | GPIO5/SCL/D1          |            |          | IO10                    |            | IE       | Used by OLED Shield |
| I2C SDA	 | GPIO4/SDA/D2          |            |          | IO8                     | High for serial bootloader | IE, 10k pullup | Use by OLED shield
| UART     | GPIO3/RX0	           | HIGH	      |          | IO20/UORXD              | IE, WPU    |          | Note GPIO# and PIN# are not remotely the same, so be careful with the spec |
| FLASH    | GPIO0/D3              |	HIGH      | HIGH     | IO7/LED                 | IE         |          | Bootstrap requirement; PIR sensor defaults to this pin |
| SCLK     | GPIO14/D5	           |            |          | IO1/A1                  |            |          |       |
| MISO     | GPIO12/D6             |            |          | IO0/A0                  |            |          |       |
| MOSI     | GPIO13/MOSI/D7        |            |          |IO4/A4                   | IE         |          |       |

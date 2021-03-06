# FYSETC-SD-WIFI
This repository contains the infomation of FYSETC SD-WIFI module

## Firmware:

You can get the firmware [here](https://github.com/FYSETC/ESPWebDAV).

## Problems

***The following problems occur in the SD-WIFI module, which may be due to insufficient power supply or signal problems.***

![](SD-WIFI_1.bmp)

### Fix 1 :

The power supply of the USB interface connected to the SD-WIFI module is insufficient, if it is the host, change the USB interface to the rear; If it is a notebook computer, it is best to connect the power supply, directly connect to the USB port, do not connect to the extension dock.

### Fix 2 :

If the above method does not work, put the module as close to the wifi signal source as possible, or change to a strong wifi signal source, the signal is too weak will lead to connection errors.

### Fix 3 :

If Fix 2 cannot be implemented for some reason, the PHY mode of the module can be changed to enhance the module signal.

| WIFI_PHY_MODE     | Description                                                  |
| ----------------- | ------------------------------------------------------------ |
| WIFI_PHY_MODE_11B | The range is the largest, the speed is the slowest, and the power consumption is the most. |
| WIFI_PHY_MODE_11G | Medium range, speed and power consumption.                   |
| WIFI_PHY_MODE_11N | The range, power consumption is the smallest and the speed is the fastest. |

Modify firmware：

1. Open firmware with [arduino](https://www.arduino.cc/) software.
2. Global search“WiFi.setPhyMode”；
3. Navigate to“WiFi.setPhyMode(WIFI_PHY_MODE_11N); ”；
4. Replace the parentheses with "WIFI_PHY_MODE_11B" or "WIFI_PHY_MODE_11G"
5. Recompile and upload to the module。

## References

Firmware Compile and upload：https://github.com/FYSETC/ESPWebDAV
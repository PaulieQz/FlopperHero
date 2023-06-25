Use the following table to select the appropriate files and place them at the corresponding address
    - Enter the address shown as the blue text in the appropriate space and add the file linked to that blue text  

|            | ESP32 Marauder v4, v6, Kit, Mini | Flipper Zero WiFi Dev Board | Flipper Zero Multi Board S3 | WiFi Dev Board Pro/LDDB/NodeMCU-32S/ESP32 Wemos D1 Mini |
| ---------- | -------------------------------- | --------------------------- | --------------------------- | ------------------ |
| Bootloader | [0x1000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/MarauderV4/esp32_marauder.ino.bootloader.bin) | [0x1000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroDevBoard/esp32_marauder.ino.bootloader.bin) | [0x0](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroMultiBoardS3/esp32_marauder.ino.bootloader.bin) | [0x1000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/MarauderV4/esp32_marauder.ino.bootloader.bin) | 
| Partitions | [0x8000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/MarauderV4/esp32_marauder.ino.partitions.bin) | [0x8000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroDevBoard/esp32_marauder.ino.partitions.bin) | [0x8000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroMultiBoardS3/esp32_marauder.ino.partitions.bin) | [0x8000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/MarauderV4/esp32_marauder.ino.partitions.bin) |
| Boot App   | [0xE000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroMultiBoardS3/boot_app0.bin) | [0xE000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroMultiBoardS3/boot_app0.bin) | [0xE000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroMultiBoardS3/boot_app0.bin) | [0xE000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroMultiBoardS3/boot_app0.bin) |
| Firmware   | [0x10000](https://github.com/justcallmekoko/ESP32Marauder/releases/latest) | [0x10000](https://github.com/justcallmekoko/ESP32Marauder/releases/latest) | [0x10000](https://github.com/justcallmekoko/ESP32Marauder/releases/latest) | [0x10000](https://github.com/justcallmekoko/ESP32Marauder/releases/latest) |

  - Use the following table to select the proper Marauder binary for your hardware  

| Hardware | Binary Version |
| -------- | -------------- |
| v4 (OG) | `_old_hardware.bin` |
| v6 | `_new_hardware.bin` |
| Kit | `_kit.bin` |
| Mini | `_mini.bin` |
| Flipper Zero | `_flipper.bin` |
| MutliBoard S3 | `_multiboardS3.bin` |
| LDDB/NodeMCU/Wemos | `_lddb.bin` |
| Dev Board Pro | `_marauder_dev_board_pro.bin` |

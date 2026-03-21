# loraguide

Hello! In this guide, you will create a custom Meshtastic-enabled LORA board with a microcontroller, antenna, radio chip, and other things.

## First things first

To start your project, we need to download KiCad. KiCad is an open-source software for designing circuit boards, or PCBs. We can use the terms interchangably.

Go to https://www.kicad.org/download/ and install the version for your OS. After that finishes, create a new project. Name it anything you want, but I will name mine Loraguide.

After that finishes, you should be on a screen that looks like this: 

<img width="1919" height="1144" alt="image" src="https://github.com/user-attachments/assets/536174dc-1196-41cc-aec2-be0c0d904739" />


## The schematic

The first step to designing a circuit board is the schematic. A schematic is essentially a wiring diagram, to show which components connect to what. That means it is very important that we follow a few design rules when creating our schematic:

 - Power symbols always point up
 - Ground symbols always point down
 - Net labels can be used instead of wires

These may not make sense right now, but you should keep track of them for later in the guide.

First, click **Schematic Editor** on the main project page. This will open a new window with a sheet of paper, and a lot of buttons. Don't worry! This guide will keep it simple, you won't need to memorize dozens of shortcuts. Optionally you can learn a few.


First, hit the **A** key. This will open up a _third_ window, which is the symbol chooser. In the top left, there is a search bar. Type in "esp32-s3", which will have a few options. 

<img width="858" height="664" alt="image" src="https://github.com/user-attachments/assets/7c6b7388-1b3c-4758-83cc-29ade888a8ab" />

Select the **ESP32-S3-WROOM-1**. This is the microcontroller we will use for this project. Next, hit OK. A projection of the microcontroller's pins will appear under your mouse, put it somewhere in the middle of your schematic. You should end up with something like this: 

<img width="1324" height="925" alt="image" src="https://github.com/user-attachments/assets/77bcbd40-a3b2-4a43-acab-a2c9cb5ef784" />


Next, we want to place our radio chip. We will use the **SX1262**, which is a low-power long range radio. Search SX1262 in the symbol chooser, and select the first result. Place it to the left of the ESP32. These are the two main components of our board, so now it is time to handle power

## Power system

Our power system is complex, but don't let that scare you! I will break it into simple parts.

### Organization

To keep our schematic organized and uncluttered, we want to use **Power Symbols** instead of

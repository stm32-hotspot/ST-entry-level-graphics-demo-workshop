# ST entry level GUIs Demo Workshop <!-- omit from toc -->

You will find in this repository all the material used during the session and the associated collateral to replicate the activities on your own, during the workshop or afterwards.

---

## Table of contents <!-- omit from toc -->
- [1. Prerequisites](#1-prerequisites)
  - [1.1. Hardware](#11-hardware)
  - [1.2. Software](#12-software)
    - [1.2.1. TouchGFX Designer](#121-touchgfx-designer)
    - [1.2.2. VS Code&reg;](#122-microsoft-vscode)
- [2. Sanity Check](#2-sanity-check)
  - [2.1 Create a basic TouchGFX project](#21-create-a-basic-touchgfx-project)
  - [2.2 Build project in VS Code&reg;](#22-build-project-in-vscode)
- [3. Hands-on](#3-hands-on)

## 1. Prerequisites

### 1.1. Hardware

The hardware setup consists in 2 boards:

  |[NUCLEO-C5A3ZG](https://www.st.com/en/evaluation-tools/nucleo-c5a3zg.html#sample-buy)|[RVA15MD](https://riverdi.com/product/015-nucleo-64)|
  |:---------------:|:--------:|
  | STM32C5A3ZGT6 MCU with FPU | 1.54 inches SPI display with touch capabilities |
  | Cortex&reg;-M33 running at 144Mhz | 240 per 240 pixels - 16-bits color depth |
  | 1 MBytes internal FLASH - 256 KBytes RAM | 8 MBytes SPI NOR FLASH |
  |<img src="./img/NUCLEO-C5A3ZG.png" width ="250" />|<img src="./img/RVA15MD.png" width ="250" />|
  |[Datasheet](https://www.st.com/resource/en/datasheet/stm32c5a3zg.pdf)|[Datasheet](https://download.riverdi.com/RVA15MD-NUC64A/DS_RVA15MD-NUC64A_Rev.1.2.pdf?_gl=1*dizkq7*_gcl_au*MTk3Mjc5NDAxMC4xNzc0NTM4MTQ1LjIxMjAxNTE1NjcuMTc3NjI0ODk5Mi4xNzc2MjQ5MDAy)|

### 1.2. Software

#### 1.2.1. TouchGFX Designer
  [🔼Top](#table-of-contents)  
  
The current version is the 4.26.1.

The TouchGFX Designer installer cannot be downloaded in a standalone way, it is included in the TouchGFX expansion pack for STM32CubeMX.

- Download [X-CUBE-TOUCHGFX](https://www.st.com/en/embedded-software/x-cube-touchgfx.html)

- Extract the installer `X-CUBE-TOUCHGFX\4.26.1\Utilities\PC_Software\TouchGFXDesigner\TouchGFX-4.26.1.msi`  
  ![TouchGFXDesignerInstaller](./img/TouchGFX-Designer_Installer.gif)

- Run the installer and prefer the default installation folder on `C:\` drive.  

#### 1.2.2. VS Code&reg;
  [🔼Top](#table-of-contents)  

- Download and install VS Code&reg; from [Visual Studio Code Download](https://code.visualstudio.com/download)

- Install the extension [STM32CubeIDE for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=stmicroelectronics.stm32-vscode-extension)
  - Open VS Code&reg; 

  - Create a new `Workshop` profile. This step is recommended if you use VS Code&reg; for other purpose, in this dedicated profile you will install only the pacakges needed for STM32 programming and avoid any kind of incompatibility between packages.  
    ![Create a profile](./img/VSCode-Create_Profile.gif)  

  - Open Extensions panel and search for "STM32CubeIDE extension for VSCode", install, dependencies will get installed automatically  
    ![Install Extension](./img/VSCode-STM32CubeIDE_Extension.gif)  

> Usefull links on VS Code&reg; extension  
> [Guide](https://github.com/stm32-hotspot/Guide_STM32CubeIDE_for_Visual_Studio_Code)  
> [Official user Manuel](https://www.st.com/resource/en/user_manual/um3512-stm32cube-for-visual-studio-code-installation-guide-stmicroelectronics.pdf)  

## 2. Sanity Check
Before starting the lab, let's check that your setup is functional.
If you manage to complete all the following steps you will be ready not only to follow the hands-on part of this workshop but also start prototyping on STM32C5!

- Plug the Riverdi display on the NUCLEO-C5A3ZG morpho connector, once plugged the text on each board with the same orientation should be read in the same direction, see below.  

  <img src="./img/NUCLEO-C5A3ZG_RVA15MD.png" width ="250" />

### 2.1 Create a basic TouchGFX project
  [🔼Top](#table-of-contents)  
  
  1. Launch TouchGFX Designer and create an empty project using the NUCLEO-C5A3ZG template  
    ![TouchGFX-Create-NUCLEO-C5A-Project](./img/TouchGFX-Designer_Create_C5_Project.gif)

  2. Insert a box widget in the main screen and set color to red (or any color)  
    ![TouchGFX-Designer-Insert-Box](./img/TouchGFX-Designer_Insert_Box.gif)
  
  3. Generate the code  
    ![TouchGFX-Designer-Generate-Code](./img/TouchGFX-Designer_Generate_Code.gif)

### 2.2 Build project in VS Code&reg;
  [🔼Top](#table-of-contents)  
  
  1. Open VS Code&reg;, be sure to be set the right Profile and open the project folder  
    ![VS Code&reg;-Open-Project](./img/VSCode-Open_Project.gif)

  2. Setup the project (in case you missed the popup window)  
    ![VS Code&reg;-Setup-Project](./img/VSCode-Setup_Project.gif)

  3. Build the project  
    ![VS Code&reg;-Build-Project](./img/VSCode-Build_Project.gif)

  4. Plug the board and launch a debug session then click on "Go", if the board screen turns to red, sanity check is successfull!  
    ![VS Code&reg;-Launch-Debug](./img/VSCode-Launch_Debug.gif)

## 3. Hands-on
  [🔼Top](#table-of-contents)  
  
  Follow the link [Hands-on](./hands_on_part.md)



# ST entry level GUIs Demo Workshop <!-- omit from toc -->

You will find in this repository all the material used during the session and the associated collateral to replicate the activities on your own, during the workshop or afterwards.

---

## Table of contents <!-- omit from toc -->
- [1. Prerequisites](#1-prerequisites)
  - [1.1. Hardware](#11-hardware)
  - [1.2. Software](#12-software)
    - [1.2.1. TouchGFX Designer](#121-touchgfx-designer)
    - [1.2.2. Microsoft VSCode](#122-microsoft-vscode)
- [2. Sanity Check](#2-sanity-check)
  - [2.1 Create a basic TouchGFX project](#21-create-a-basic-touchgfx-project)
  - [2.2 Build project in VSCode](#22-build-project-in-vscode)
- [3. Hands-on](#3-hands-on)

## 1. Prerequisites

### 1.1. Hardware

The hardware setup consists in 2 boards:

  |[NUCLEO-C5A3ZG](https://www.st.com/en/evaluation-tools/nucleo-c5a3zg.html#sample-buy)|[RVA15MD](https://riverdi.com/product/015-nucleo-64)|
  |:---------------:|:--------:|
  |<img src="./img/NUCLEO-C5A3ZG.png" width ="250" />|<img src="./img/RVA15MD.png" width ="250" />|

### 1.2. Software

#### 1.2.1. TouchGFX Designer

The current version is the 4.26.1.

The TouchGFX Designer installer cannot be downloaded in a standalone way, it is included in the TouchGFX expansion pack for STM32CubeMX.

- Download [X-CUBE-TOUCHGFX](https://www.st.com/en/embedded-software/x-cube-touchgfx.html)
- Extract the `X-CUBE-TOUCHGFX\4.26.1\Utilities\PC_Software\TouchGFXDesigner\TouchGFX-4.26.1.msi`
  ![TouchGFXDesignerInstaller](./img/TouchGFX-Designer_Installer.gif)
- Run the installer and prefer the default installation folder on `C:\` drive.

[🔼 Back to top](#table-of-contents)

#### 1.2.2. Microsoft VSCode

- Download and install VSCode from [Visual Studio Code Download](https://code.visualstudio.com/download)
- Install the extension [STM32CubeIDE for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=stmicroelectronics.stm32-vscode-extension)
  - Open VSCode 
  - Create a new `stm32Cube` profile (recommended)
    ![Create a profile](./img/VSCode-Create_Profile.gif)
  - Open Extensions panel
  - Search for "STM32CubeIDE extension for VSCode", install, dependencies will get installed automatically
    ![Install Extension](./img/VSCode-STM32CubeIDE_Extension.gif)

> [!NOTE]
> [VSCode Guide](https://github.com/stm32-hotspot/Guide_STM32CubeIDE_for_Visual_Studio_Code)
> [Official user Manuel](https://www.st.com/resource/en/user_manual/um3512-stm32cube-for-visual-studio-code-installation-guide-stmicroelectronics.pdf)

[🔼 Back to top](#table-of-contents)

## 2. Sanity Check
Before starting the lab, let's check that your setup is functional.

- Plug the Riverdi display on the NUCLEO-C5A3ZG morpho connector

  <img src="./img/NUCLEO-C5A3ZG_RVA15MD.png" width ="250" />

### 2.1 Create a basic TouchGFX project
  - Launch TouchGFX Designer and create an empty project using the NUCLEO-C5A3ZG template
    ![TouchGFX-Create-NUCLEO-C5A-Project](./img/TouchGFX-Designer_Create_C5_Project.gif)

  - Insert a box widget in the main screen and set color to red
    ![TouchGFX-Designer-Insert-Box](./img/TouchGFX-Designer_Insert_Box.gif)
  
  - Generate the code
    ![TouchGFX-Designer-Generate-Code](./img/TouchGFX-Designer_Generate_Code.gif)

[🔼 Back to top](#table-of-contents)

### 2.2 Build project in VSCode

  - Open VSCode, be sure to be set the right Profile and open the project folder
    ![VSCode-Open-Project](./img/VSCode-Open_Project.gif)

  - Setup the project (in case you missed the popup window)
    ![VSCode-Setup-Project](./img/VSCode-Setup_Project.gif)

  - Build the project
    ![VSCode-Build-Project.gif](./img/VSCode-Build_Project.gif)

  - Plug the board and launch a debug session then click on "Go", if the board screen turns to red, sanity check is successfull!
    ![VSCode-Launch-Debug](./img/VSCode-Launch_Debug.gif)

[🔼 Back to top](#table-of-contents)

## 3. Hands-on

  Follow the link [Hands-on](./hands_on_part.md)



# ST entry-level GUIs Demo Workshop


# Table of contents
1. [Introduction](#introduction)
2. [Prerequisites](#paragraph1)
    1. [Hardware](#subparagraph1)
    2. [Software](#subparagraph2)

3. [Sanity Check](#paragraph2)
4. [Hands-on](#paragraph3)

## This is the introduction <a name="introduction"></a>
You will find in this repository all the material used during the session and the associated collateral to replicate the activities on your own, during the workshop or afterwards.

## Prerequisites <a name="paragraph1"></a>

### Hardware <a name="subparagraph1"></a>

|[NUCLEO-C5A3ZG](https://www.st.com/en/evaluation-tools/nucleo-c5a3zg.html#sample-buy)|[RVA15MD](https://riverdi.com/product/015-nucleo-64)|
|:---------------:|:--------:|
|<img src="./img/NUCLEO-C5A3ZG.png" width ="250" />|<img src="./img/RVA15MD.png" width ="250" />|

### Software <a name="subparagraph2"></a>

#### TouchGFX Designer version 4.26.1

The TouchGFX Designer installer cannot be downloaded in a standalone way, it is included in the TouchGFX expansion pack for STM32CubeMX.

- Donwload [X-CUBE-TOUCHGFX](https://www.st.com/en/embedded-software/x-cube-touchgfx.html)
- Extract the X-CUBE-TOUCHGFX\4.26.1\Utilities\PC_Software\TouchGFXDesigner\TouchGFX-4.26.1.msi
  ![TouchGFXDesignerInstaller](./img/TouchGFX-Designer_Installation.gif)
- Run the installer
  
#### Microsoft VSCode with extension "STM32CudeIDE for VSCode"

- Download and install VSCode from [Visual Studio Code Download](https://code.visualstudio.com/download)
- Install the extension
  - Open VSCode 
  - Create a new "stm32Cube" profile (recommended)

  ![Create a profile](./img/VSCode-Create_Profile.gif)
  - Open Extensions panel
  - Search for "STM32CubeIDE extension for VSCode"

  ![Install Extension](./img/VSCode-STM32CubeIDE_Extension.gif)
  - Install, dependencies will get installed automatically


## Sanity Check <a name="paragraph2"></a>
Before starting the lab, let's check that your setup is functional.

- Plug the Riverdi display on the NUCLEO-C5A3ZG morpho connector

  <img src="./img/NUCLEO-C5A3ZG_RVA15MD.png" width ="250" />

- Launch TouchGFX Designer and create an empty project using the NUCLEO-C5A3ZG template
  ![TouchGFX-Create-NUCLEO-C5A-Project](./img/TouchGFX-Create-NUCLEO-C5A-Project.gif)

- Open VSCode, be sure to be set the right Profile and open the project folder

## Hands-on <a name="paragraph3"></a>




# ST entry level GUIs Demo Workshop [🔼 Home](./README.md#table-of-contents)<!-- omit from toc -->

This hands-on demonstrate in practice some of the TouchGFX Designer dedicated to FLASH usage reduction when working on entry-level MCUs.
---

## Table of contents <!-- omit from toc -->
- [This hands-on demonstrate in practice some of the TouchGFX Designer dedicated to FLASH usage reduction when working on entry-level MCUs.](#this-hands-on-demonstrate-in-practice-some-of-the-touchgfx-designer-dedicated-to-flash-usage-reduction-when-working-on-entry-level-mcus)
- [1. Introduction](#1-introduction)
  - [1.1 Troubleshoot](#11-troubleshoot)
  - [1.2 Default VSCode extension Build analyzer](#12-default-vscode-extension-build-analyzer)
- [2 TouchGFX Designer RGB Compression feature](#2-touchgfx-designer-rgb-compression-feature)
- [3 TouchGFX Designer L8 compression feature](#3-touchgfx-designer-l8-compression-feature)

## 1. Introduction
  This hands-on is focus on external FLASH usage reduction when using bitmaps, it illustrates the following article from the TouchGFX Documentation:
    [Flash-limited GUI Development](https://support.touchgfx.com/docs/flash-limited)

### 1.1 Troubleshoot
  TouchGFX Designer installation should complete without issues.

  VSCode installation and especially the STM32CubeIDE extension may be lead to some issues, the most common one concerns [proxy/certificate configuration](https://community.st.com/t5/stm32-mcus/how-to-configure-the-proxy-or-certificate-for-stm32cubeide-for/ta-p/846476).

    [🔼 Back to top](#table-of-contents)

### 1.2 Default VSCode extension Build analyzer

  The default build analyzer included in the current version of the extension does not give the proper information on external FLASH usage.
  For this hands-on another build analyzer extension 'STM32 Build Analyze" will be used.
  Feel free to use any ohther extension.
  ![VSCode-STM32BuildAnalyzer-Extension](VSCode-STM32BuildAnalyzer_Extension.gif)
  
    [🔼 Back to top](#table-of-contents)

## 2 TouchGFX Designer RGB Compression feature

  - Insert an image widget
  - Generate the code
  - Rebuild the Visual Studio project and check the SPI_FLASH usage
    ![VSCode-View-build-Analyzer](./img/VSCode-View_build_Analyzer.gif)
  - Enable RGB compression in TouchGFX Designer project
  - Generate the code
  - Rebuild the Visual Studio project and check the SPI_FLASH usage

    [🔼 Back to top](#table-of-contents)

## 3 TouchGFX Designer L8 compression feature

  - Import an existing demo to the project
  - Generate the code
  - Rebuild the Visual Studio project and check the SPI_FLASH usage
  - Enable L8_RGB565 compression in TouchGFX Designer project for some images
  - Generate the code
  - Rebuild the Visual Studio project and check the SPI_FLASH usage

    [🔼 Back to top](#table-of-contents)
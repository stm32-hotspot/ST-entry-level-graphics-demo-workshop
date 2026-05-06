# ST entry level GUIs Demo Workshop <!-- omit from toc -->

This hands-on demonstrate in practice some of the TouchGFX Designer features dedicated to FLASH usage reduction when working on entry-level MCUs.  
[🔼 Home](./README.md#table-of-contents)  

---

## Table of contents <!-- omit from toc -->
- [1. Introduction](#1-introduction)
  - [1.1. Troubleshoot](#11-troubleshoot)
  - [1.2. Default VS Code extension Build analyzer](#12-default-vs-code-extension-build-analyzer)
  - [1.3 NUCLEO-C5A3ZG TBS considerations](#13-nucleo-c5a3zg-tbs-considerations)
- [2. TouchGFX Designer RGB Compression feature](#2-touchgfx-designer-rgb-compression-feature)
- [3. TouchGFX Designer L8 compression feature](#3-touchgfx-designer-l8-compression-feature)
- [4. Other compression techniques](#4-other-compression-techniques)

## 1. Introduction  

  This hands-on is focus on external FLASH usage reduction when using bitmaps, it illustrates the following article from the TouchGFX Documentation:  
  [Flash-limited GUI Development](https://support.touchgfx.com/docs/flash-limited)

### 1.1. Troubleshoot
  [🔼Top](#table-of-contents)  
  
  TouchGFX Designer installation should complete without issues.

  VSCode installation and especially the STM32CubeIDE extension may be lead to some issues, the most common one concerns [proxy/certificate configuration](https://community.st.com/t5/stm32-mcus/how-to-configure-the-proxy-or-certificate-for-stm32cubeide-for/ta-p/846476).  

### 1.2. Default VS Code extension Build analyzer
  [🔼Top](#table-of-contents)  
  
  The default build analyzer included in the current version of the extension does not give the proper information on external FLASH usage.  
  For this hands-on a third party extension 'STM32 Build Analyze" will be used.
  Feel free to use any other extension or the VS Code&reg; build output window that provides accurate information on external FLASH usage, but not the details.

### 1.3. NUCLEO-C5A3ZG TBS considerations
  [🔼Top](#table-of-contents)  
  
  A TouchGFX Board Setup (TBS) is read-to-use, complete setup for a specific ST evaluation kit such as a Discovery kit (with embedded display and memory) or a Nucleo kit combined with a display shield (as the one used in this hands-on).  
  
  A TBS contains all the low-level drivers for the selected display as well the Board Initialization Code needed for the display interface (e.g. SPI, FMC, LTDC).  
  The TBSs are based on a STM32CubeMX configuration, so it is possible for you to modify the configuration if you want to experiment or add access to more peripherals.

  The following TBS will be used in this hands-on and has some specificities:  
     ![TBS for NUCLEO-C5A3ZG + RVA15MD](./img/TBS-NUCLEO-C5A3ZG_RVA15MD.png)

  The STM32C5 family is the first one to come with the updated ecosystem: [STM32CubeMX2](https://community.st.com/t5/developer-news/introducing-stm32cubemx2-a-new-flavor-of-stm32cubemx-tool/ba-p/885793)
  
  If TouchGFX 4.x.x is fully supported in the STM32CubeMX tool (as an expansion pack) it is not yet the case on STM32CubeMX2.
  This integration will be guaranteed by the TouchGFX 5.x.x currently under development.

  The impact on the NUCLEO-C5A3ZG + RVA15MD TBS are:
  - A valid STM32CubeMX2 project (i.e. an .ioc2 file) is provided in the template, containing the proper peripheral configuration based on the Cube ecosystem evolution.
  - The link with TouchGFX is done outside STM32CubeMX2, manually modifying some generated files (e.g. CMakeLists.txt)
  - Code generation from STM32CubeMX2 must be done with care as it may break the link with TouchGFX
  - Only VS Code&reg; IDE (cmake) is currently supported
  - Some minor warnings may be visible in the VS Code&reg; build output windows

  As a summary, the TBS usage (in the current version 3.0.2) is mainly recommended for prototyping on the NUCLEO-C5A3ZG with the Riverdi display and code generation must only be done in the TouchGFX Designer, not from STM32CubeMX2.
  
  Guidelines on how to use TouchGFX 4.x.x with STM32CubeMX2 projects is available on the [TouchGFX Documentation](https://support.touchgfx.com/docs/introduction/welcome).
  
## 2. TouchGFX Designer RGB Compression feature
  [🔼Top](#table-of-contents)  
  
  In this section 2 screens will be defined each one including an image widget populated with a Bitmap from the stock images.
  FLASH usage will be analyzed first without any optimization and then with compression option.
  
  1. Insert a second screen using the dedicated button  
    ![3.1.Designer_Add_Screen](./img/3.1.Designer_Add_Screen.gif)
  
  2. Insert an image widget in first screen  
    ![3.2.Designer_Insert_Image_Screen1](./img/3.2.Designer_Insert_Image_Screen1.gif)
  
  3. Insert an image widget in second screen  
    ![3.3.Designer_Insert_Image_Screen2](./img/3.3.Designer_Insert_Image_Screen2.gif)
  
  4. Generate the code  
    ![3.4.Designer_Generate_Code](./img/3.4.Designer_Generate_Code.gif)
  
  5. [Optional] Install a build analyzer, e.g. STM32 Build Analyser  
    ![3.5.VSCode_Install_Build_analyzer](./img/3.5.VSCode_Install_Build_analyzer.gif)
  
  6. Build the VS Code&reg; project and check the SPI_FLASH usage  
    ![3.6.VSCode_Build_project](./img/3.6.VSCode_Build_project.gif)
  
  7. Check the SPI_FLASH usage  
    ![3.7.VSCode_Check_SPI_Usage](./img/3.7.VSCode_Check_SPI_Usage.gif)
  
  8. In the image tab, change the image included in the first screen:  
    - set image format to RGB565  
    - enable compression  
    ![3.8.Designer_screen1_bitmap_compression](./img/3.8.Designer_screen1_bitmap_compression.gif)
  
  9. Still in the image tab, change the image included in the second screen:  
    - image format to ARGB8888 (because selected image has transparency)  
    - enable compression  
    ![3.9.Designer_screen2_bitmap_compression](./img/3.9.Designer_screen2_bitmap_compression.gif)
  
  10. Generate the code from the Designer  
    ![3.10.Designer_generate_code](./img/3.10.Designer_generate_code.gif)
  
  11. Rebuild the VS Code&reg; project and check the new SPI_FLASH usage  
    ![3.11.VSCode_rebuild](./img/3.11.VSCode_rebuild.gif)

| Default Configuration | Compression enabled |
|:---------------:|:--------:|
| <img src="./img/3.7.VSCode_Check_SPI_Usage_Before_Compression.png" width ="600" />|<img src="./img/3.11.VSCode_Check_SPI_Usage_After_Compression.png" width ="600" />|

  With very simple image format settings the external FLASH usage has been significantly reduced (around 28% compression ratio).

## 3. TouchGFX Designer L8 compression feature
  [🔼Top](#table-of-contents)  
  
  In this section an existing demo will be imported.
  FLASH usage will be analyzed first without any optimization and after changing the format of some input images to a Look-up table one.

  After demonstrating how to import an existing example or demo to a project we will use the 8-bits Look-Up Table format on some assets of the demo to reduce the footprint of the demo.

  1. Import the existing knob display demo to the project  
    ![4.1.Designer_Import_Existing_Demo](./img/4.1.Designer_Import_Existing_Demo.gif)  
  
  2. Generate the code  
    ![4.2.Designer_Generate](./img/4.2.Designer_Generate.gif)  
  
  3. Rebuild the VS Code&reg; project and check the SPI_FLASH usage  
    ![4.3.VSCode_Rebuild_Check_Footprint](./img/4.3.VSCode_Rebuild_Check_Footprint.gif)  
  
  4. Enable L8_RGB565 compression in TouchGFX Designer project for some images  
    Select several images then apply a parameter to selected images  
    ![4.4.Designer_Change_Several_Images_Format](./img/4.4.Designer_Change_Several_Images_Format.gif)  
  
  5. Generate the code  
    ![4.5.Designer_Generate](./img/4.5.Designer_Generate.gif)  
  
  6. Rebuild the VS Code&reg; project and check the SPI_FLASH usage  
    ![4.6.VSCode_Rebuild_Check_Footprint](./img/4.6.VSCode_Rebuild_Check_Footprint.gif)  

| Default (RGB565 format) - 1 pixel = 2 bytes color value | Look-Up Table format (L8_RGB565) - 1 pixel = 1 byte LUT index (actual color in LUT) |
|:---------------:|:--------:|
| <img src="./img/4.3.VSCode_Rebuild_Check_Footprint.png" width ="600" />|<img src="./img/4.6.VSCode_Rebuild_Check_Footprint.png" width ="600" />|

> Note that the L8 format involves a per-image overhead in internal FLASH to store the Look-Up Table:  
>  <img src="./img/4.6.VSCode_Rebuild_Check_Footprint_LUT.png" width ="600" />  
>  
>  The gain in FLASH footprint remains significant despite this, but it must be kept in mind and balanced against the use of RGB compression techniques that has no ROM impact but a computing one at runtime (for the decompression process).  

## 4. Other compression techniques
  [🔼Top](#table-of-contents)  
  
  Other FLASH usage reduction techniques are available in the TouchGFX Designer, notably the use of Vector Graphics for both images and text.
  However, Vector Graphics processing may have a significant impact on RAM and CPU load and it is usually recommended on MCU with dedicated hardware accelerator (i.e. NeoChrom) or high-end ones, which is out of the scope of this workshop. 

  Please refer to the following article for more details:
  [Flash-limited GUI Development](https://support.touchgfx.com/docs/flash-limited)
  

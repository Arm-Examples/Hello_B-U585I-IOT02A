# Hello example for B-U585I-IOT02A

Simple Hello World example for STMicroelectronics [**B-U585I-IOT02A**](https://www.st.com/en/evaluation-tools/b-u585i-iot02a.html) Discovery kit.
This example prints "Hello World" and a counter value via the standard output which is routed to the debug console through Virtual COM port.

[![Keil Studio Cloud - Import Project](https://img.shields.io/badge/Keil_Studio_Cloud-Import_Project-0091bd?logo=arm&logoColor=0091bd)](https://studio.keil.arm.com/?import=https://github.com/Arm-Examples/Hello_B-U585I-IOT02A.git)
[![example workflow](https://img.shields.io/github/actions/workflow/status/Arm-Examples/Hello_B-U585I-IOT02A/ci.yml?logo=arm&logoColor=0091bd&label=Example%20Published)](https://www.keil.arm.com/) 
[![CMSIS Compliance](https://img.shields.io/github/actions/workflow/status/Arm-Examples/Hello_B-U585I-IOT02A/verify.yml?logo=arm&logoColor=0091bd&label=CMSIS%20Compliance)](https://www.keil.arm.com/cmsis) 

## Prerequisites

### Tools:
 - [CMSIS-Toolbox v2.0.0](https://github.com/Open-CMSIS-Pack/cmsis-toolbox/releases) or newer
 - [Microsoft Visual Studio Code](https://code.visualstudio.com/download) with Keil Studio Pack extension (optional, alternatively CLI can be used)
 - [Arm Compiler 6](https://developer.arm.com/Tools%20and%20Software/Arm%20Compiler%20for%20Embedded) (default toolchain, automatically installed when using Visual Studio Code with vcpkg)
 - [Arm GNU Toolchain](https://developer.arm.com/downloads/-/arm-gnu-toolchain-downloads) (alternate toolchain, automatically installed when using Visual Studio Code with vcpkg)

## Build Solution/Project

The example is configured to use **Arm Compiler 6** by default. In order to use **Arm GNU Toolchain** change the 'compiler' node in [hello.csolution.yml.](hello.csolution.yml) to:
```
  compiler: GCC
```

### Using Visual Studio Code with extensions

Required tools described in file 'vcpkg-configuration.json' should be automatically installed by vcpkg. You can see the status of vcpkg in the status bar.

Required CMSIS packs need to be also installed. In case a required pack is missing, a notification window will pop-up to install the missing pack.

Open the 'CMSIS' view from the side bar, select desired 'Build Type' and press the 'Build' button.

### Using Command Line Interface (CLI)

Download required packs (not required when the packs are already available) by executing the following commands:
   ```sh
   csolution list packs -s hello.csolution.yml -m >packs.txt
   cpackget update-index
   cpackget add -f packs.txt
   ```
Build the project by executing the following command:
```sh
cbuild hello.csolution.yml
```

## Run the application

### Using Visual Studio Code with extensions

 - Connect the board's ST-LINK USB to the PC (provides also power).
 - Open the 'CMSIS' view from the side bar:
   - Press the 'Run' button and wait until the image is programmed and starts running.
   - Press the 'Open Serial' button and select the board's serial port with 115200 baud rate.
 - Observe the terminal output.

 ### Using Drag-and-drop programming or external programmer and terminal

 - Connect the board's ST-LINK USB to the PC (provides also power).
 - Program the image (.hex) using Drag-and-drop programming or use external programmer.
 - Open terminal on the PC and connect to the board's serial port with 115200 baud rate.
 - Observe the terminal output.

## Debug the application

### Using Visual Studio Code with extensions

Open the 'CMSIS' view from the side bar and press the 'Debug' button.

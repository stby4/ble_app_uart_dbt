# DBT code for nRF52850 IoT system demo

> Tested with the Nordic nRF5 SDK v15.3.0.

This code is based on the Nordic UART Service (NUS) demo project.

# Installation
The [nRF5 SDK](https://www.nordicsemi.com/Software-and-Tools/Software/nRF5-SDK) must be installed.

- Go to "nRF5_SDK_15.3.0_59ac345\examples\ble_peripheral".
- Execute `git clone git@github.com:stby4/ble_app_uart_dbt.git ble_app_uart_dbt`.
- Open the Segger Embedded Studio (SES) project in `ble_app_uart_dbt\pca10056\s140\ses`.
- Use "Build and Run" in SES to compile the code and flash it on the connected nRF52840 DK.

# Usage
## Hardware setup

- Use the Python code from [fhnw-iot-gateway](git@github.com:stby4/fhnw-iot-gateway.git) on a Raspberry Pi with the u-blox LARA-R2 module, as described [here](https://github.com/stby4/fhnw-iot-gateway#python).
- Switch to the "feature/demo" branch of the `fhnw-iot-gateway` repository (`git checkout feature/demo`).
- Open the SES project from "nRF5_SDK_15.3.0_59ac345\examples\ble_central\ble_app_uart_c\pca10056\s140\ses" and run it on a second nRF52840 DK. This device will act as the BLE central.
- Connect the BLE central via USB to the Raspberry Pi and start the `RXTX` Python program on the Raspberry Pi.
- If not already done, follow the steps in [Installation](#Installation). This nRF52840 will act as the BLE peripheral and simulate a DBT.

## Execution
The demo code sends fake sensor data from the DBT to [dweet.io/follow/scary-weather](dweet.io/follow/scary-weather). The response from dweet.io is sent back to the DBT and printed on the console of the DBT (the Terminal Emulator in SES can be used for output).

Press _Button 1_ on the DBT to send data to dweet.io.
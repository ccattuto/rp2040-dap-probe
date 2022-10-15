cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)
project(dap-probe C CXX ASM)
pico_sdk_init()

add_executable(dap-probe)

target_sources(dap-probe PUBLIC
		CMSIS_5/CMSIS/DAP/Firmware/Source/DAP.c
		CMSIS_5/CMSIS/DAP/Firmware/Source/SW_DP.c
        src/usb_descriptors.c
        src/main.c
        )

target_include_directories(dap-probe PUBLIC
		"CMSIS_5/CMSIS/Core/Include"
		"CMSIS_5/CMSIS/DAP/Firmware/Include"
        "inc")

target_link_libraries(dap-probe PUBLIC pico_stdlib tinyusb_device tinyusb_board)

pico_add_extra_outputs(dap-probe)

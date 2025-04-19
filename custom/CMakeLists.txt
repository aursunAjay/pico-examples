cmake_minimum_required(VERSION 3.12)

# include(pico_sdk_import.cmake)

project(custom)

#add_definitions(-DPendSV_Handler=isr_pendsv)
#add_definitions(-DSysTick_Handler=isr_systick)

add_executable(${PROJECT_NAME} main.c tx_initialize_low_level.S demo_threadx.c)

pico_enable_stdio_usb(${PROJECT_NAME} 1)

pico_add_extra_outputs(${PROJECT_NAME})


target_link_libraries(${PROJECT_NAME} pico_stdlib cmsis_core azrtos::threadx)
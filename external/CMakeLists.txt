add_subdirectory(esp8266-cmake/main)
add_subdirectory(esp8266-cmake/arduino)

### SSD1306 Display Library
file(GLOB PUBSUBCLIENT_LIB_SRC
    ${CMAKE_CURRENT_LIST_DIR}/esp8266-oled-ssd1306/*.c
    ${CMAKE_CURRENT_LIST_DIR}/esp8266-oled-ssd1306/*.cpp
)

add_library(ssd1306 STATIC
    ${PUBSUBCLIENT_LIB_SRC}
)

target_include_directories(ssd1306 PUBLIC
    ${CMAKE_CURRENT_LIST_DIR}/esp8266-oled-ssd1306
)

target_link_libraries(ssd1306 PUBLIC
    arduino
    esp8266wire
)


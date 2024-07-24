cmake_minimum_required(VERSION 3.18)

project("rtaudio-playground")

find_package(RtAudio 7.0.0 EXACT REQUIRED) # PATHS "P:\\Downloads\\cpp-libraries\\portaudio\\build\\cmake\\portaudio")

if(RtAudio_FOUND)
    message(STATUS "YES")
else()
    message(STATUS "NO")
endif()

add_executable(${PROJECT_NAME}
    "src/main.cpp"
)

target_link_libraries(${PROJECT_NAME} RtAudio::rtaudio)
target_link_options(${PROJECT_NAME} PRIVATE "-static")

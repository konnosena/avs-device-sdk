cmake_minimum_required(VERSION 3.1 FATAL_ERROR)

add_definitions("-DACSDK_LOG_MODULE=defaultClient")
add_library(DefaultClient SHARED
    DefaultClient.cpp)
target_include_directories(DefaultClient PUBLIC
    "${DefaultClient_SOURCE_DIR}/include")
target_link_libraries(DefaultClient 
    AVSCommon 
    ACL 
    ADSL 
    AFML 
    AIP 
    Alerts
    PlaybackController
    SpeakerManager
    SpeechSynthesizer
    Settings
    TemplateRuntime
    AudioPlayer
    AVSSystem
    ContextManager)

# install target
asdk_install()

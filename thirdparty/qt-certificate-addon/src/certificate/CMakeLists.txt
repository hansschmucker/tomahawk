if( NOT WIN32 )
        add_definitions( -fPIC )
endif()

list(APPEND qtcertificateaddon_INCLUDE_DIRECTORIES
    ${QT_INCLUDES}
    ${QT_QTCORE_INCLUDE_DIR}
    ${QT_QTNETWORK_INCLUDE_DIR}
    ${CMAKE_CURRENT_BINARY_DIR}
)

list(APPEND qtcertificateaddon_SOURCES
    certificatebuilder.cpp
    keybuilder.cpp
    certificaterequestbuilder.cpp
    randomgenerator.cpp
    certificaterequest.cpp
    utils.cpp
)

include_directories(${qtcertificateaddon_INCLUDE_DIRECTORIES})
add_library(qtcertificateaddon STATIC ${qtcertificateaddon_SOURCES})
set_target_properties(
    qtcertificateaddon
        PROPERTIES
            AUTOMOC TRUE
)
qt5_use_modules(qtcertificateaddon Core Network)



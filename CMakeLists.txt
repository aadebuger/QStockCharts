project( QStockCharts )
#export CMAKE_PREFIX_PATH=/Users/aadebuger/Qt5.7.1/5.7/clang_64/lib/cmake
cmake_minimum_required( VERSION 2.8.11 )

# root of your msvc14 x64 prebuild, there should be a `/lib/cmake` dir
set( CMAKE_PREFIX_PATH ${CMAKE_PREFIX_PATH} $ENV{QT5_DIR} )
set( CMAKE_PREFIX_PATH ${CMAKE_PREFIX_PATH} "C:/Qt/VS2015x64/Qt5.6.0/5.6/msvc2015_64" ) # remember to add `C:\Qt\VS2015x64\Qt5.6.0\5.6\msvc2015_64\bin` to %PATH%
set( CMAKE_INCLUDE_CURRENT_DIR ON )
set( CMAKE_AUTOMOC ON )

#find_package( Qt5Widgets   REQUIRED )
find_package( Qt5  COMPONENTS WebEngine  WebEngineCore  WebView WebEngineWidgets Widgets )

#qt5_wrap_ui( UI_HEADERS mainwindow.ui )
qt5_add_resources( QRCS res.qrc )
add_executable( ${PROJECT_NAME} main.cpp mainwindow.cpp  qmytoolbar.cpp qmydata.cpp qmycanvas.cpp  ${UI_HEADERS} ${QRCS} )
target_link_libraries( ${PROJECT_NAME} Qt5::Widgets Qt5::WebEngine Qt5::WebEngineCore Qt5::WebView Qt5::WebEngineWidgets )

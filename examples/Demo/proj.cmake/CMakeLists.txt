cmake_minimum_required (VERSION 2.6)
project (Demo)

add_subdirectory(../../../ oxygine-framework)
add_definitions(${OXYGINE_DEFINITIONS})
include_directories(${OXYGINE_INCLUDE_DIRS})
link_directories(${OXYGINE_LIBRARY_DIRS})

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
add_executable(Demo ../src/Counter.cpp ../src/main.cpp ../src/example.cpp ../src/test.cpp
	../src/Counter.h ../src/TestAlphaHitTest.h ../src/TestBox9Sprite.h ../src/TestClipRect.h
	../src/TestColorFont.h ../src/TestTweenGlow.h ../src/TestCounter.h ../src/TestDrag.h ../src/TestHttp.h ../src/TestInputText.h ../src/TestManageRes.h ../src/TestMask.h ../src/TestPerf.h ../src/TestPolygon.h ../src/TestProgressBar.h ../src/TestRender2Texture.h ../src/TestSliding.h ../src/TestTexel2Pixel.h ../src/TestText.h ../src/TestTextureFormat.h ../src/TestTweenText.h ../src/TestTweens.h ../src/TestUserShader.h ../src/TestUserShader2.h ../src/TestTweenAlphaFade.h ../src/example.h ../src/test.h )

if (WIN32) #disable console mode for VC++
	set_target_properties(Demo PROPERTIES WIN32_EXECUTABLE TRUE)
endif(WIN32)

target_link_libraries(Demo ${OXYGINE_CORE_LIBS})
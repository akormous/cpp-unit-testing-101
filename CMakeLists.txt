<<<<<<< HEAD
cmake_minimum_required(VERSION 3.14)
set(PROJECT_NAME_STR CPPUnitTesting)
project(${PROJECT_NAME_STR} C CXX)

# GoogleTest requires at least C++11
set(CMAKE_CXX_STANDARD 11)

include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/609281088cfefc76f9d0ce82e1ff6c30cc3591e5.zip
)
# For Windows: Prevent overriding the parent project's compiler/linker settings
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

enable_testing()

add_executable(
  hello_test
  hello_test.cc
)
target_link_libraries(
  hello_test
  gtest_main
)

include(GoogleTest)
gtest_discover_tests(hello_test)
=======
cmake_minimum_required(VERSION 3.14)
 
# Locate GTest
find_package(GTest REQUIRED)
include_directories(${GTEST_INCLUDE_DIRS})
 
# Link runTests with what we want to test and the GTest and pthread library
add_executable(executeTests sqrt_tests.cpp)
target_link_libraries(executeTests ${GTEST_LIBRARIES} pthread)
>>>>>>> 44984020741bac0a34fd8e4e95cef8b23973edd3

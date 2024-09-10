cmake_minimum_required(VERSION 3.16)
project(gnss_comm)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic -Wno-comment)
endif()


# find dependencies
find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)

find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
        msg/GnssBestXYZMsg.msg
        msg/GnssEphemMsg.msg
        msg/GnssGloEphemMsg.msg
        msg/GnssMeasMsg.msg
        msg/GnssObsMsg.msg
        msg/GnssPVTSolnMsg.msg
        msg/GnssSvsMsg.msg
        msg/GnssTimeMsg.msg
        msg/GnssTimePulseInfoMsg.msg
        msg/StampedFloat64Array.msg
        DEPENDENCIES std_msgs
)

if(BUILD_TESTING)
    find_package(ament_lint_auto REQUIRED)
    # the following line skips the linter which checks for copyrights
    # uncomment the line when a copyright and license is not present in all source files
    #set(ament_cmake_copyright_FOUND TRUE)
    # the following line skips cpplint (only works in a git repo)
    # uncomment the line when this package is not in a git repo
    #set(ament_cmake_cpplint_FOUND TRUE)
    ament_lint_auto_find_test_dependencies()
endif()

ament_export_dependencies(rosidl_default_runtime)
ament_package()





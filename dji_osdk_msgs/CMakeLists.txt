cmake_minimum_required(VERSION 3.16)
project(dji_osdk_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic -Wno-comment)
endif()


# find dependencies
find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
        # msg/BatteryState.msg
        # msg/BatteryWholeInfo.msg
        msg/FCTimeInUTC.msg
        msg/FlightAnomaly.msg
        # msg/Gimbal.msg
        msg/GPSUTC.msg
        # msg/HMSPushInfo.msg
        # msg/JoystickParams.msg
       #  msg/MissionHotpointTask.msg
        # msg/MissionWaypoint.msg
       #  msg/MissionWaypointAction.msg
        # msg/MissionWaypointTask.msg
        # msg/MobileData.msg
        # msg/PayloadData.msg
        # msg/SmartBatteryDynamicInfo.msg
        # msg/SmartBatteryState.msg
        msg/VOPosition.msg
        # msg/Waypoint.msg
        # msg/WaypointList.msg
        # msg/WaypointV2.msg
        # msg/WaypointV2Action.msg
        # msg/WaypointV2AircraftControlActuator.msg
        # msg/WaypointV2AircraftControlActuatorFlying.msg
        # msg/WaypointV2AircraftControlActuatorRotateHeading.msg
        # msg/WaypointV2AssociateTrigger.msg
        # msg/WaypointV2CameraActuator.msg
        # msg/WaypointV2CameraActuatorFocalLengthParam.msg
        # msg/WaypointV2CameraActuatorFocusParam.msg
        # msg/WaypointV2Config.msg
        # msg/WaypointV2GimbalActuator.msg
        # msg/WaypointV2GimbalActuatorRotationParam.msg
        # msg/WaypointV2InitSetting.msg
        # msg/WaypointV2MissionEventPush.msg
        # msg/WaypointV2IntervalTrigger.msg
        # msg/WaypointV2MissionStatePush.msg
        # msg/WaypointV2ReachpointTrigger.msg
        # msg/WaypointV2SampleReachPointTrigger.msg
        # msg/WaypointV2TrajectoryTrigger.msg
        DEPENDENCIES builtin_interfaces std_msgs 
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





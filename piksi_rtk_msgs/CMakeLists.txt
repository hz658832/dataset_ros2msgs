cmake_minimum_required(VERSION 3.8)
project(piksi_rtk_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)

find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  # "msg/AgeOfCorrections.msg"
  # "msg/BaselineEcef.msg"
  # "msg/BaselineHeading.msg"
  # "msg/BaselineNed.msg"
  # "msg/BasePosEcef.msg"
  # "msg/BasePosLlh.msg"
  # "msg/DeviceMonitor_V2_3_15.msg"
  # "msg/Dops.msg"
  # "msg/DopsMulti.msg"
  # "msg/ExtEvent.msg"
  # "msg/GpsTime.msg"
  # "msg/GpsTimeMulti.msg"
  # "msg/Heartbeat.msg"
  # "msg/ImuAuxMulti.msg"
  # "msg/ImuRawMulti.msg"
  # "msg/InfoWifiCorrections.msg"
  # "msg/Log.msg"
  # "msg/MagRaw.msg"
  # "msg/MeasurementState_V2_4_1.msg"
  # "msg/Observation.msg"
  # "msg/PosEcef.msg"
  # "msg/PosEcefCov.msg"
  # "msg/PositionSampling.msg"
  # "msg/PositionWithCovariance.msg"
  # "msg/PositionWithCovarianceStamped.msg"
  # "msg/PosLlh.msg"
  # "msg/PosLlhCov.msg"
  # "msg/PosLlhMulti.msg"
  # "msg/ReceiverState.msg"
  # "msg/ReceiverState_V2_2_15.msg"
  # "msg/ReceiverState_V2_3_15.msg"
  "msg/ReceiverStateV241.msg"
  # "msg/ReceiverState_V2_6_5.msg"
  # "msg/TrackingState.msg"
  # "msg/TrackingState_V2_2_15.msg"
  # "msg/TrackingState_V2_3_15.msg"
  # "msg/TrackingState_V2_6_3.msg"
  # "msg/UartState.msg"
  # "msg/UartState_V2_3_15.msg"
  # "msg/UtcTimeMulti.msg"
  # "msg/VelEcef.msg"
  # "msg/VelEcefCov.msg"
  # "msg/VelNed.msg"
  # "msg/VelNedCov.msg"
  # "msg/VelocityWithCovariance.msg"
  # "msg/VelocityWithCovarianceStamped.msg"
  DEPENDENCIES std_msgs geometry_msgs
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

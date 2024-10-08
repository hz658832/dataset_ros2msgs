cmake_minimum_required(VERSION 3.8)
project(irt_nav_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(nav_msgs REQUIRED)
find_package(tf2_geometry_msgs REQUIRED)

find_package(rosidl_default_generators REQUIRED)


rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/Microstrain.msg"
  "msg/PVAGeodetic.msg"
  "msg/SFusion.msg"
  "msg/SimulationTime.msg"
  "msg/RTCML1E1.msg"
  "msg/RTCMV3.msg"
  "msg/RTCM1004.msg"
  "msg/RTCM1005.msg"
  "msg/PPS.msg"
  "msg/GNSSObs.msg"
  "msg/GNSSObsPreProcessed.msg"
  "msg/FGOState.msg"
  "msg/Error2GT.msg"
  "msg/ElapsedTimeFGO.msg"
  "msg/RTCMRaw.msg"
  "msg/SolLS.msg"
  "msg/PVTLS.msg"
  "msg/NavFilter.msg"
  "msg/Residual.msg"
  "msg/GaussianComponent.msg"
  "msg/GaussianMixture.msg"
  "msg/DumperOdom.msg"
  "msg/SatelliteData.msg"
  "msg/PRFactorWeights.msg"
  "msg/HybridStatistics.msg"
  "msg/SatLabel.msg"
  "msg/GNSSCorrection.msg"
  "msg/GNSSLabeling.msg"
  "msg/OdomInfo.msg"
  "msg/Residuals.msg"
  "msg/Correvit.msg"
  "msg/CorrevitStatus.msg"
  "msg/CorrevitVelAngle.msg"
  "msg/CorrevitPitchRoll.msg"
  "msg/DoubleStamped.msg"
  "msg/ResidualSample.msg"
  "msg/FactorResidual.msg"
  "msg/FactorResiduals.msg"
  "msg/SensorProcessingReport.msg"
  DEPENDENCIES std_msgs geometry_msgs nav_msgs tf2_geometry_msgs
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

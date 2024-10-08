cmake_minimum_required(VERSION 3.10)
project(novatel_oem7_msgs)


set(CMAKE_CXX_STANDARD 14)

set(MSG_DEPS std_msgs)


find_package(ament_cmake 		REQUIRED)
find_package(rosidl_default_generators 	REQUIRED)
find_package(std_msgs 			REQUIRED)


set(MSG_FILES
  srv/Oem7AbasciiCmd.srv
  msg/Oem7RawMsg.msg
  msg/Oem7Header.msg
  msg/BESTPOS.msg
  msg/BESTUTM.msg
  msg/BESTVEL.msg
  msg/HEADING2.msg
  msg/INSCONFIG.msg
  msg/INSPVA.msg
  msg/INSPVAX.msg
  msg/INSSTDEV.msg
  msg/CORRIMU.msg
  msg/IMURATECORRIMU.msg
  msg/RXSTATUS.msg
  msg/TIME.msg
  msg/INSExtendedSolutionStatus.msg
  msg/INSFrame.msg
  msg/INSReceiverStatus.msg
  msg/INSResetType.msg
  msg/INSSourceStatus.msg
  msg/INSUpdate.msg
  msg/BestExtendedSolutionStatus.msg
  msg/InertialSolutionStatus.msg
  msg/INSAlignmentMode.msg
  msg/INSOutputFrame.msg
  msg/PositionOrVelocityType.msg
  msg/Rotation.msg
  msg/RotationalOffset.msg
  msg/SolutionStatus.msg
  msg/SolutionSource.msg
  msg/Translation.msg
  msg/TranslationOffset.msg
  msg/CLOCKMODEL.msg
  msg/DUALANTENNAHEADING.msg
  msg/GALCLOCK.msg
  msg/GALFNAVEPHEMERIS.msg
  msg/GALINAVEPHEMERIS.msg
  msg/GALIONO.msg
  msg/GPSEPHEM.msg
  msg/IONUTC.msg
  msg/RANGEData.msg
  msg/RANGE.msg
  msg/SBASALMANAC.msg
  msg/NAVICSYSCLOCK.msg
  msg/GALFNAVEPHEMERISArray.msg
  msg/GALINAVEPHEMERISArray.msg
  msg/GPSEPHEMArray.msg
  msg/RANGEArray.msg
  msg/INSCOV.msg
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${MSG_FILES}
  DEPENDENCIES ${MSG_DEPS}
)


ament_export_dependencies(rosidl_default_runtime)
ament_package()

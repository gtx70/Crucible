cmake_minimum_required(VERSION 3.27)

set(CMAKE_DOTNET_SDK "Microsoft.NET.Sdk")

# Target framework moniker
set(CMAKE_DOTNET_TARGET_FRAMEWORK "net8.0-windows10.0.19041.0")

project(CrucibleSolution LANGUAGES CSharp)

add_subdirectory(Crucible)

set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT Crucible)

# Add this native debug profile for the user convenience
file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/launchSettings.json
  DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/Crucible/Properties
)
add_executable(json_parser main.cc)

find_package(spdlog REQUIRED)
find_package(jsoncpp REQUIRED)
find_package(dbg-macro REQUIRED)
find_package(CLI11 REQUIRED)

target_link_libraries(json_parser PRIVATE learn_cpp::learn_cpp_options
                                          learn_cpp::learn_cpp_warnings)
target_link_system_libraries(
  json_parser
  PRIVATE
  spdlog::spdlog
  JsonCpp::JsonCpp
  dbg-macro::dbg-macro
  CLI11::CLI11)

target_include_directories(json_parser PRIVATE "${CMAKE_BINARY_DIR}/configured_files/include")

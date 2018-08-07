cmake_minimum_required (VERSION 2.8)

# 项目信息
project (Demo)

# 查找目录下的所有源文件
# 并将名称保存到 DIR_SRCS 变量
aux_source_directory(. DIR_SRCS)

# 添加 math 子目录
add_subdirectory(src)

# 指定生成目标
add_executable(Demo ${DIR_SRCS})

# 添加链接库
target_link_libraries(Demo MathFunctions)

enable_testing()

add_test (test_5_2 Demo 5 2)

set_tests_properties (test_5_2
  PROPERTIES PASS_REGULAR_EXPRESSION "is 25")

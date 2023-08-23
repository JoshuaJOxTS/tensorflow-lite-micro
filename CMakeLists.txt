cmake_minimum_required(VERSION 3.16)
project(tflite-micro C CXX)

set(CMAKE_CXX_STANDARD 17)

file(GLOB_RECURSE SRCS
     "*.h"
     "*.cc"
     "*.cpp"
     "*.c"
)

add_compile_definitions(CMSIS_NN)
# add_compile_definitions(TF_LITE_STATIC_MEMORY)

add_library(tflite-micro ${SRCS})

target_include_directories(tflite-micro PUBLIC
     ${PROJECT_SOURCE_DIR}
     third_party/gemmlowp 
     third_party/kissfft 
     third_party/ruy
     third_party/flatbuffers/include
     third_party/cmsis 
     third_party/cmsis/CMSIS/Core/Include
     third_party/cmsis/CMSIS/DSP/Include
     third_party/cmsis/CMSIS/NN/Include
     third_party/cmsis_nn
     third_party/cmsis_nn/Include
      )
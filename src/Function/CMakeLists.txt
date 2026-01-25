# CMakeLists.txt for Function module

# Create library for Function
add_library(FunctionLib MODULE
    Function.cpp
)

# Link against LLVM libraries
llvm_map_components_to_libnames(llvm_libs core support)
target_link_libraries(FunctionLib ${llvm_libs})

# Set output directory
set_target_properties(FunctionLib PROPERTIES
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
)

# Include directories
target_include_directories(FunctionLib PRIVATE
    ${CMAKE_SOURCE_DIR}/include
    ${CMAKE_CURRENT_SOURCE_DIR}
)

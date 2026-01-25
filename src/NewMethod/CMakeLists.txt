# CMakeLists.txt for NewMethod module

# Create library for NewMethod
add_library(NewMethodLib MODULE
    NewMethod.cpp
)

# Link against LLVM libraries
llvm_map_components_to_libnames(llvm_libs core support)
target_link_libraries(NewMethodLib ${llvm_libs})

# Set output directory
set_target_properties(NewMethodLib PROPERTIES
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
)

# Include directories
target_include_directories(NewMethodLib PRIVATE
    ${CMAKE_SOURCE_DIR}/include
    ${CMAKE_CURRENT_SOURCE_DIR}
)

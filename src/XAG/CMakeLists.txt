# CMakeLists.txt for XAG module

# Create library for XAG
add_library(XAGLib MODULE
    XAG.cpp
)

# Link against LLVM libraries
llvm_map_components_to_libnames(llvm_libs core support)
target_link_libraries(XAGLib ${llvm_libs})

# Set output directory
set_target_properties(XAGLib PROPERTIES
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
)

# Include directories
target_include_directories(XAGLib PRIVATE
    ${CMAKE_SOURCE_DIR}/include
    ${CMAKE_CURRENT_SOURCE_DIR}
)

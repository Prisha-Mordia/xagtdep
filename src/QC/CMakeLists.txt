# CMakeLists.txt for QC module

# Create library for QC
add_library(QCLib MODULE
    QC.cpp
)

# Link against LLVM libraries
llvm_map_components_to_libnames(llvm_libs core support)
target_link_libraries(QCLib ${llvm_libs})

# Set output directory
set_target_properties(QCLib PROPERTIES
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
)

# Include directories
target_include_directories(QCLib PRIVATE
    ${CMAKE_SOURCE_DIR}/include
    ${CMAKE_CURRENT_SOURCE_DIR}
)

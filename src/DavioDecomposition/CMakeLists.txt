# CMakeLists.txt for DavioDecomposition module

# Create library for DavioDecomposition
add_library(DavioDecompositionLib MODULE
    DavioDecomposition.cpp
)

# Link against LLVM libraries
llvm_map_components_to_libnames(llvm_libs core support)
target_link_libraries(DavioDecompositionLib ${llvm_libs})

# Set output directory
set_target_properties(DavioDecompositionLib PROPERTIES
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
)

# Include directories
target_include_directories(DavioDecompositionLib PRIVATE
    ${CMAKE_SOURCE_DIR}/include
    ${CMAKE_CURRENT_SOURCE_DIR}
)

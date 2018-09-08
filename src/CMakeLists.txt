set_source_files_properties(${SOURCE_FILES} PROPERTIES CYTHON_IS_CXX FALSE)
cython_add_standalone_executable(${PROJECT_NAME} MAIN_MODULE "main.pyx")

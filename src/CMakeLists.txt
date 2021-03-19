
cmake_minimum_required(VERSION 3.16)
project(RedCar)

# temp, should be changed to normal name.
set(executable run)

# set standard.
set(CMAKE_CXX_STANDARD 17)

# add warnings.
add_compile_options(-Wall -Wextra -Wconversion)

# include all .cpp files.
file(GLOB CPP_FILES src/*.cpp)

# include all .h files.
file(GLOB H_FILES include/${PROJECT_NAME}/*.h)

# create executable.
add_executable(${executable} 
	${CPP_FILES} 
	${H_FILES}
	)



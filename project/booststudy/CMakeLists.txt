﻿#
# 项目名
#
SET(PROGRAM_NAME booststudy)


#
# 设置可执行文件生成目录
#
SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)


#
# 遍历递归当前目录获取源文件
#
RECURSE_CURRENT_DIRECTORY_SOURCE_FILE(SOURCE_FILES)


#
# 链接源文件, 生成可执行文件
#
ADD_EXECUTABLE(${PROGRAM_NAME} ${SOURCE_FILES})

#
# 链接库文件
#
TRAVERSE_LIBRARY_FOR_PROGRAM_NAME(/usr/local/mysql/lib/libmysqlclient.so.21)



##################################################################################

TRAVERSE_INCLUDE_FOR_PROGRAM_NAME(/usr/local/mysql/include)


#
# 定义当前目录下源文件分组
#
IF(WIN32 OR APPLE)

	#
	# 遍历递归当前目录定义源文件分组
	#
	RECURSE_CURRENT_DIRECTORY_SOURCE_FILE_GROUP()

ENDIF()

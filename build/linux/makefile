NAME 		= dropbox_handler
DIR_BUILD :=  $(realpath $(dir $(lastword $(MAKEFILE_LIST))))
DIR_SRC := $(realpath $(DIR_BUILD)/../../src)
DIR_INCLUDE := $(realpath $(DIR_BUILD)/../../include)
COMP		= gcc
LINK		= ld
MAKEDEPEND 	= gcc -MM -MF


ifeq ($(DIR_BUILD_UTILS),)
export DIR_BUILD_UTILS = $(realpath $(DIR_BUILD)/../../../../build_utils/linux)
endif
include $(DIR_BUILD_UTILS)/project.properties

export DIR_INSTALL=$(DIR_GRASSROOTS_INSTALL)/handlers

VPATH	= \
	$(DIR_SRC) 
	
INCLUDES = \
	-I$(DIR_INCLUDE) \
	-I$(DIR_GRASSROOTS_UTIL_INC) \
	-I$(DIR_GRASSROOTS_UTIL_INC)/containers \
	-I$(DIR_GRASSROOTS_UTIL_INC)/io \
	-I$(DIR_GRASSROOTS_HANDLER_INC) \
	-I$(DIR_GRASSROOTS_SERVER_INC) \
	-I$(DIR_GRASSROOTS_SERVICES_INC) \
	-I$(DIR_GRASSROOTS_NETWORK_INC) \
	-I$(DIR_GRASSROOTS_PARAMS_INC) \
	-I$(DIR_JANSSON_INC) \
	-I$(DIR_DROPBOX_INC) \
	-I$(DIR_UUID_INC)

SRCS 	= \
	dropbox_handler.c 
	
CPPFLAGS = -DDROPBOX_HANDLER_EXPORTS

LDFLAGS += \
	-L$(DIR_GRASSROOTS_HANDLE_LIB) -l$(GRASSROOTS_HANDLE_LIB_NAME) \
	-L$(DIR_GRASSROOTS_NETWORK_LIB) -l$(GRASSROOTS_NETWORK_LIB_NAME) \
	-L$(DIR_GRASSROOTS_UTIL_LIB) -l$(GRASSROOTS_UTIL_LIB_NAME) \
	-L$(DIR_DROPBOX_LIB) -ldropbox
	

include $(DIR_BUILD_UTILS)/generic_makefiles/shared_library.makefile


TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#==================================================
# build a support library

LIBRARY_IOC += libjson

# xxxRecord.h will be created from xxxRecord.dbd
#DBDINC += xxxRecord
# install libjson.dbd into <top>/dbd
DBD += libjson.dbd
INC += libjson.h JSONOptions.h _internal/Source/JSONDefs.h \
	_internal/Source/JSONDefs/GNU_C.h _internal/Source/JSONDefs/Unknown_C.h _internal/Source/JSONDefs/Visual_C.h _internal/Source/JSONDefs/Strings_Defs.h

USR_CXXFLAGS += -DLIBJSON_EXPORTS
# specify all source files to be compiled and added to the library
libjson_SRCS += internalJSONNode.cpp JSONAllocator.cpp JSONChildren.cpp \
                 JSONDebug.cpp JSONIterators.cpp JSONMemory.cpp JSONNode.cpp \
                 JSONNode_Mutex.cpp JSONPreparse.cpp JSONStream.cpp JSONValidator.cpp \
                 JSONWorker.cpp JSONWriter.cpp libjson.cpp 
SRC_DIRS += $(TOP)/libjsonApp/src/_internal/Source
libjson_LIBS += $(EPICS_BASE_IOC_LIBS)

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

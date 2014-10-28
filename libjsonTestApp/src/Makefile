TOP = ../..

# OS=$(shell uname)
# ifeq ($(OS), Darwin)
	# fastflag = -fast -ffast-math -fexpensive-optimizations
# else
	# fastflag = -O3 -ffast-math -fexpensive-optimizations
# endif

# COMPILER ?= g++

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

### NOTE: there should only be one build.mak for a given IOC family and this should be located in the ###-IOC-01 directory

#=============================
# Build the IOC application libjsonTest
# We actually use $(APPNAME) below so this file can be included by multiple IOCs

# this definition is used in build.mak
APPNAME=libjsonTest

PROD_IOC = $(APPNAME)

# libjsonTest.dbd will be created and installed
DBD += $(APPNAME).dbd

# libjsonTest.dbd will be made up from these files:
$(APPNAME)_DBD += base.dbd

$(APPNAME)_LIBS += libjson
USR_INCLUDES += -I $(TOP)/libjsonApp/src/_internal/Source

# libjsonTest_registerRecordDeviceDriver.cpp derives from libjsonTest.dbd

USR_CXXFLAGS += -DLIBJSON_EXPORTS

$(APPNAME)_SRCS += $(APPNAME)_registerRecordDeviceDriver.cpp

$(APPNAME)_SRCS += TestAssign.cpp TestChildren.cpp \
	TestComments.cpp TestConverters.cpp TestCtors.cpp \
	TestEquality.cpp TestFunctions.cpp TestInequality.cpp \
	TestInspectors.cpp TestIterators.cpp TestMutex.cpp \
	TestNamespace.cpp TestRefCounting.cpp TestSuite.cpp \
	TestWriter.cpp TestString.cpp UnitTest.cpp \
	TestStreams.cpp TestBinary.cpp \
	TestSharedString.cpp \

# Build the main IOC entry point on workstation OSs.
$(APPNAME)_SRCS_DEFAULT += main.cpp
#$(APPNAME)_SRCS_DEFAULT += main.cpp
$(APPNAME)_SRCS_vxWorks += -nil-

# Add support from base/src/vxWorks if needed
#$(APPNAME)_OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary

# Finally link to the EPICS Base libraries
$(APPNAME)_LIBS += $(EPICS_BASE_IOC_LIBS)

#===========================

#----------------------------------------
#  ADD RULES AFTER THIS LINE

# single:
	# $(COMPILER) 
	# ../Source/internalJSONNode.cpp \
	# ../Source/JSONChildren.cpp ../Source/JSONDebug.cpp \
	# ../Source/JSONIterators.cpp ../Source/JSONMemory.cpp \
	# ../Source/JSONNode_Mutex.cpp ../Source/JSONNode.cpp \
	# ../Source/JSONWorker.cpp ../Source/JSONWriter.cpp \
	# ../Source/libjson.cpp ../Source/JSONValidator.cpp \
	# ../Source/JSONStream.cpp ../Source/JSONAllocator.cpp \
    	# ../Source/JSONPreparse.cpp \
	# ../TestSuite2/JSON_Base64/json_decode64.cpp \
	# ../TestSuite2/JSON_Base64/json_encode64.cpp \
	# ../TestSuite2/JSONDebug/JSON_ASSERT_SAFE.cpp \
	# ../TestSuite2/JSONDebug/JSON_ASSERT.cpp \
	# ../TestSuite2/JSONDebug/JSON_FAIL_SAFE.cpp \
	# ../TestSuite2/JSONDebug/JSON_FAIL.cpp \
	# ../TestSuite2/JSONGlobals/jsonSingleton.cpp \
	# ../TestSuite2/JSONValidator/isValidArray.cpp \
	# ../TestSuite2/JSONValidator/isValidMember.cpp \
	# ../TestSuite2/JSONValidator/isValidNamedObject.cpp \
	# ../TestSuite2/JSONValidator/isValidNumber.cpp \
	# ../TestSuite2/JSONValidator/isValidObject.cpp \
	# ../TestSuite2/JSONValidator/isValidPartialRoot.cpp \
	# ../TestSuite2/JSONValidator/isValidRoot.cpp \
	# ../TestSuite2/JSONValidator/isValidString.cpp \
	# ../TestSuite2/JSONValidator/securityTest.cpp \
	# ../TestSuite2/NumberToString/_areFloatsEqual.cpp \
	# ../TestSuite2/NumberToString/_atof.cpp \
	# ../TestSuite2/NumberToString/_ftoa.cpp \
	# ../TestSuite2/NumberToString/_itoa.cpp \
	# ../TestSuite2/NumberToString/_uitoa.cpp \
	# ../TestSuite2/NumberToString/getLenSize.cpp \
	# ../TestSuite2/NumberToString/isNumeric.cpp \
     # -Wfatal-errors -DNDEBUG $(fastflag) -pipe -o testapp

# debug:
	# $(COMPILER) main.cpp TestAssign.cpp TestChildren.cpp \
	# TestComments.cpp TestConverters.cpp TestCtors.cpp \
	# TestEquality.cpp TestFunctions.cpp TestInequality.cpp \
	# TestInspectors.cpp TestIterators.cpp TestMutex.cpp \
	# TestNamespace.cpp TestRefCounting.cpp TestSuite.cpp \
	# TestWriter.cpp TestString.cpp UnitTest.cpp \
	# TestValidator.cpp TestStreams.cpp TestBinary.cpp \
	# RunTestSuite2.cpp TestSharedString.cpp \
	# ../Source/internalJSONNode.cpp \
	# ../Source/JSONChildren.cpp ../Source/JSONDebug.cpp \
	# ../Source/JSONIterators.cpp ../Source/JSONMemory.cpp \
	# ../Source/JSONNode_Mutex.cpp ../Source/JSONNode.cpp \
	# ../Source/JSONWorker.cpp ../Source/JSONWriter.cpp \
	# ../Source/libjson.cpp ../Source/JSONValidator.cpp \
	# ../Source/JSONStream.cpp ../Source/JSONAllocator.cpp \
    	# ../Source/JSONPreparse.cpp \
	# ../TestSuite2/JSON_Base64/json_decode64.cpp \
	# ../TestSuite2/JSON_Base64/json_encode64.cpp \
	# ../TestSuite2/JSONDebug/JSON_ASSERT_SAFE.cpp \
	# ../TestSuite2/JSONDebug/JSON_ASSERT.cpp \
	# ../TestSuite2/JSONDebug/JSON_FAIL_SAFE.cpp \
	# ../TestSuite2/JSONDebug/JSON_FAIL.cpp \
	# ../TestSuite2/JSONGlobals/jsonSingleton.cpp \
	# ../TestSuite2/JSONValidator/isValidArray.cpp \
	# ../TestSuite2/JSONValidator/isValidMember.cpp \
	# ../TestSuite2/JSONValidator/isValidNamedObject.cpp \
	# ../TestSuite2/JSONValidator/isValidNumber.cpp \
	# ../TestSuite2/JSONValidator/isValidObject.cpp \
	# ../TestSuite2/JSONValidator/isValidPartialRoot.cpp \
	# ../TestSuite2/JSONValidator/isValidRoot.cpp \
	# ../TestSuite2/JSONValidator/isValidString.cpp \
	# ../TestSuite2/JSONValidator/securityTest.cpp \
	# ../TestSuite2/NumberToString/_areFloatsEqual.cpp \
	# ../TestSuite2/NumberToString/_atof.cpp \
	# ../TestSuite2/NumberToString/_ftoa.cpp \
	# ../TestSuite2/NumberToString/_itoa.cpp \
	# ../TestSuite2/NumberToString/_uitoa.cpp \
	# ../TestSuite2/NumberToString/getLenSize.cpp \
	# ../TestSuite2/NumberToString/isNumeric.cpp \
     # -Wfatal-errors -DJSON_DEBUG -pipe -o testapp

# small:
	# $(COMPILER) main.cpp TestAssign.cpp TestChildren.cpp \
	# TestComments.cpp TestConverters.cpp TestCtors.cpp \
	# TestEquality.cpp TestFunctions.cpp TestInequality.cpp \
	# TestInspectors.cpp TestIterators.cpp TestMutex.cpp \
	# TestNamespace.cpp TestRefCounting.cpp TestSuite.cpp \
	# TestWriter.cpp TestString.cpp UnitTest.cpp \
	# TestValidator.cpp TestStreams.cpp TestBinary.cpp \
	# RunTestSuite2.cpp TestSharedString.cpp \
	# ../Source/internalJSONNode.cpp \
	# ../Source/JSONChildren.cpp ../Source/JSONDebug.cpp \
	# ../Source/JSONIterators.cpp ../Source/JSONMemory.cpp \
	# ../Source/JSONNode_Mutex.cpp ../Source/JSONNode.cpp \
	# ../Source/JSONWorker.cpp ../Source/JSONWriter.cpp \
	# ../Source/libjson.cpp ../Source/JSONValidator.cpp \
	# ../Source/JSONStream.cpp ../Source/JSONAllocator.cpp \
    	# ../Source/JSONPreparse.cpp \
	# ../TestSuite2/JSON_Base64/json_decode64.cpp \
	# ../TestSuite2/JSON_Base64/json_encode64.cpp \
	# ../TestSuite2/JSONDebug/JSON_ASSERT_SAFE.cpp \
	# ../TestSuite2/JSONDebug/JSON_ASSERT.cpp \
	# ../TestSuite2/JSONDebug/JSON_FAIL_SAFE.cpp \
	# ../TestSuite2/JSONDebug/JSON_FAIL.cpp \
	# ../TestSuite2/JSONGlobals/jsonSingleton.cpp \
	# ../TestSuite2/JSONValidator/isValidArray.cpp \
	# ../TestSuite2/JSONValidator/isValidMember.cpp \
	# ../TestSuite2/JSONValidator/isValidNamedObject.cpp \
	# ../TestSuite2/JSONValidator/isValidNumber.cpp \
	# ../TestSuite2/JSONValidator/isValidObject.cpp \
	# ../TestSuite2/JSONValidator/isValidPartialRoot.cpp \
	# ../TestSuite2/JSONValidator/isValidRoot.cpp \
	# ../TestSuite2/JSONValidator/isValidString.cpp \
	# ../TestSuite2/JSONValidator/securityTest.cpp \
	# ../TestSuite2/NumberToString/_areFloatsEqual.cpp \
	# ../TestSuite2/NumberToString/_atof.cpp \
	# ../TestSuite2/NumberToString/_ftoa.cpp \
	# ../TestSuite2/NumberToString/_itoa.cpp \
	# ../TestSuite2/NumberToString/_uitoa.cpp \
	# ../TestSuite2/NumberToString/getLenSize.cpp \
	# ../TestSuite2/NumberToString/isNumeric.cpp \
     # -Wfatal-errors -DNDEBUG -Os -ffast-math -DJSON_LESS_MEMORY -pipe -o testapp

# test:
	# $(COMPILER) All/main.cpp  UnitTest.cpp -DNDEBUG $(fastflag) -ffast-math -fexpensive-optimizations -pipe -o testall

include $(TOP)/configure/RULES
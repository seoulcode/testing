TOPDIR:=$(shell /bin/pwd)
GTEST_DIR=$(TOPDIR)/../googletest/googletest

OBJECTS=main.o sum.o
SRCS=main.cc sum.cc
SRCS_TEST=sum.cc sum_test.cc
TARGET=run
TARGET_TEST=sum_test
INCLUDE=-I$(GTEST_DIR)/include
LDINC=-L$(GTEST_DIR)/build/lib
LD= -pthread -lgtest

$(TARGET_TEST) : $(OBJECTS)
	$(CXX) -o $(TARGET_TEST) $(OBJECTS)

all:
	$(CXX) -o $(TARGET) $(OBJECTS)

test:
	$(CXX) -o $(TARGET_TEST) $(SRCS_TEST) $(INCLUDE) $(LDINC) $(LD)
	./$(TARGET_TEST)

clean:
	rm -rf $(TARGET) $(TARGET_TEST)

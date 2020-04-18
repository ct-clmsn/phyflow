# Copyright (c) 2019-2020 Christopher Taylor
#
#  Distributed under the Boost Software License, Version 1.0. (See accompanying
#  file LICENSE_1_0.txt or copy at http://www.boost.org/LICENSE_1_0.txt)
#
BASE_DIR=$(HOME)/git
ISL_BASE_DIR=$(BASE_DIR)/isl
ISL_ROOT_DIR=$(HOME)/git/install
TIRAMISU_ROOT_DIR=$(BASE_DIR)/tiramisu

INC_FLAGS=-I$(HOME)/git/install/include -I$(ISL_ROOT_DIR)/include -I$(TIRAMISU_ROOT_DIR)/include -I$(ISL_BASE_DIR)
LIB_FLAGS=-L$(HOME)/git/install/lib -L$(ISL_ROOT_DIR)/lib -L$(TIRAMISU_ROOT_DIR)/build
LIBS=-lisl -ltiramisu
CXX_FLAGS=-g -Wall -shared -std=c++14 -fPIC $(CXX_EXT)
#-stdlib=libc++
#-D_GLIBCXX_USE_CXX11_ABI=1

PYTIRAMISU_OBJ=pytiramisu`python3.8-config --extension-suffix`
#pytiramisu.cpython-36m-x86_64-linux-gnu.so

CXX_EXT=$(INC_FLAGS) $(LIB_FLAGS)
# $(LIBS)
CXX=clang++
#CXX=g++

#all: $(PYTIRAMISU_OBJ)
#	@echo "pytiramisu build complete"

#test
#physl_isl.o: physl_isl.cpp
#	$(CXX) -O3 -std=c++17 -fPIC $(INC_FLAGS) -c physl_isl.cpp

#physl_tiramisu.o: physl_isl.o physl_tiramisu.cpp
#	$(CXX) -O3 -std=c++17 -fPIC $(INC_FLAGS) -c physl_tiramisu.cpp

#$(PYTIRAMISU_OBJ): physl_isl.o physl_tiramisu.o pytiramisu.cpp
#	$(CXX) $(CXX_FLAGS) -fPIC `python3.8 -m pybind11 --includes` pytiramisu.cpp -o $(PYTIRAMISU_OBJ) physl_isl.o physl_tiramisu.o $(CXX_EXT)

#$(PYTIRAMISU_OBJ):
all:
	$(CXX) $(CXX_FLAGS) pytiramisu.cpp  -o $(PYTIRAMISU_OBJ) `python3.8 -m pybind11 --includes` $(LIBS)
#test: physl_tiramisu.o physl_isl.o
#	$(CXX) $(CXX_FLAGS) -g $(INC_FLAGS) $(LIB_FLAGS) test.cpp -o test physl_isl.o physl_tiramisu.o $(LIBS)
#	g++ $(CXX_FLAGS) -g $(INC_FLAGS) $(LIB_FLAGS) test.cpp -o test physl_isl.o physl_tiramisu.o $(LIBS)
#test:
#	$(CXX) $(CXX_FLAGS) -g -fPIC $(INC_FLAGS) $(LIB_FLAGS) test.cpp -o test
 
clean:
	rm $(PYTIRAMISU_OBJ)

#	rm physl_isl.o
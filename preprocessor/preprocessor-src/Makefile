BASE = preprocessor
CXX ?= g++
CXXFLAGS ?= -std=c++17
CXXFLAGS += -O1
LLVM_ROOT ?= /usr/lib/llvm-17

SRCS = src/preprocessor.cc \
	src/io.cc \
	src/util.cc \
	src/clang/clang-wrapper.cc \
	src/preprocessor/cxx_ast.cc \
	src/preprocessor/graph-creator.cc \
	src/preprocessor/pragma.cc \
	src/preprocessor/types.cc \
	src/preprocessor/util.cc

all: $(BASE)

$(BASE):
	$(CXX) $(CXXFLAGS) $(SRCS) preprocessor.cpp -I$(LLVM_ROOT)/include -Iinclude -L$(LLVM_ROOT)/lib -Llib -o preprocessor -lclang -lboost_program_options -lpragma-parser

clean:
	rm -f preprocessor

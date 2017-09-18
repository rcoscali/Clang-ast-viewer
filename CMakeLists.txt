cmake_minimum_required(VERSION 2.8.9)
project(ClangAstViewer)

set(CLANG_PREFIX_PATH "/usr/local/lib/x86_64-linux-gnu/lib")

add_subdirectory(ClangUtilities)


# Find includes in corresponding build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)
# Instruct CMake to run moc automatically when needed.
set(CMAKE_AUTOMOC ON)

# Find the QtWidgets library
find_package(Qt5Widgets)

set(ClangAst_Forms MainWindow.ui)
set(ClangAst_Srcs 
	main.cpp 
	MainWindow.cpp 
	Highlighter.cpp
	AstReader.cpp
	AstModel.cpp
	CommandLineSplitter.cpp
	)

set(ClangAst_Hdrs 
	MainWindow.h 
	Highlighter.h
	AstReader.h
	AstModel.h
	CommandLineSplitter.h
	)

QT5_WRAP_UI(UIS_HDRS ${ClangAst_Forms})

# Tell CMake to create the helloworld executable
add_executable(ClangAstViewer ${ClangAst_Srcs} ${ClangAst_Hdrs} ${UIS_HDRS})


# Probably some can be removed...
target_link_libraries (ClangAstViewer 
	ClangUtilities
	${CLANG_PREFIX_PATH}clangAnalysis.a
	${CLANG_PREFIX_PATH}clangAST.a
	${CLANG_PREFIX_PATH}clangASTMatchers.a
	${CLANG_PREFIX_PATH}clangBasic.a
	${CLANG_PREFIX_PATH}clangDriver.a
	${CLANG_PREFIX_PATH}clangEdit.a
	${CLANG_PREFIX_PATH}clangFrontend.a
	${CLANG_PREFIX_PATH}clangLex.a
	${CLANG_PREFIX_PATH}clangParse.a
	${CLANG_PREFIX_PATH}clangStaticAnalyzerCore.a
	${CLANG_PREFIX_PATH}clangStaticAnalyzerCheckers.a
	${CLANG_PREFIX_PATH}clangStaticAnalyzerFrontend.a
	${CLANG_PREFIX_PATH}clangRewrite.a
	${CLANG_PREFIX_PATH}clangSema.a
	${CLANG_PREFIX_PATH}clangSerialization.a
	${CLANG_PREFIX_PATH}clangTooling.a
	${CLANG_PREFIX_PATH}LLVMBinaryFormat.a
	${CLANG_PREFIX_PATH}LLVMDebugInfoDWARF.a
	${CLANG_PREFIX_PATH}LLVMBitReader.a
	${CLANG_PREFIX_PATH}LLVMMC.a
	${CLANG_PREFIX_PATH}LLVMMCParser.a
	${CLANG_PREFIX_PATH}LLVMOption.a
	${CLANG_PREFIX_PATH}LLVMSupport.a
	${CLANG_PREFIX_PATH}LLVMProfileData.a
	${CLANG_PREFIX_PATH}LLVMCore.a
	${CLANG_PREFIX_PATH}clangAnalysis.a
	${CLANG_PREFIX_PATH}clangAST.a
	${CLANG_PREFIX_PATH}clangASTMatchers.a
	${CLANG_PREFIX_PATH}clangBasic.a
	${CLANG_PREFIX_PATH}clangDriver.a
	${CLANG_PREFIX_PATH}clangEdit.a
	${CLANG_PREFIX_PATH}clangFrontend.a
	${CLANG_PREFIX_PATH}clangLex.a
	${CLANG_PREFIX_PATH}clangParse.a
	${CLANG_PREFIX_PATH}clangStaticAnalyzerCore.a
	${CLANG_PREFIX_PATH}clangStaticAnalyzerCheckers.a
	${CLANG_PREFIX_PATH}clangStaticAnalyzerFrontend.a
	${CLANG_PREFIX_PATH}clangRewrite.a
	${CLANG_PREFIX_PATH}clangSema.a
	${CLANG_PREFIX_PATH}clangSerialization.a
	${CLANG_PREFIX_PATH}clangTooling.a
	${CLANG_PREFIX_PATH}LLVMBinaryFormat.a
	${CLANG_PREFIX_PATH}LLVMBitReader.a
	${CLANG_PREFIX_PATH}LLVMDebugInfoDWARF.a
	${CLANG_PREFIX_PATH}LLVMMC.a
	${CLANG_PREFIX_PATH}LLVMMCParser.a
	${CLANG_PREFIX_PATH}LLVMOption.a
	${CLANG_PREFIX_PATH}LLVMSupport.a
	${CLANG_PREFIX_PATH}LLVMProfileData.a
	${CLANG_PREFIX_PATH}LLVMCore.a
	/usr/lib/x86_64-linux-gnu/libreadline.a
	/usr/lib/x86_64-linux-gnu/libncurses.a
	/usr/lib/x86_64-linux-gnu/libtermcap.a
	/usr/lib/x86_64-linux-gnu/libz.a
	/usr/lib/x86_64-linux-gnu/libpthread.so
	)

# Use the Widgets module from Qt 5.
qt5_use_modules(ClangAstViewer Widgets)



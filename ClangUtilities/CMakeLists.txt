cmake_minimum_required(VERSION 2.8.9)


set(ClangUtilities_Srcs 
	TemplateUtilities.cpp 
	StringLiteralExtractor.cpp
	)
	
set(ClangUtilities_Hdrs 
	TemplateUtilities.h 
	StringLiteralExtractor.h
	)

add_library(ClangUtilities STATIC ${ClangUtilities_Srcs} ${ClangUtilities_Hdrs})



# Probably some can be removed...
target_link_libraries (ClangUtilities 
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
	${CLANG_PREFIX_PATH}LLVMDebugInfoDWARF.a
	${CLANG_PREFIX_PATH}LLVMBitReader.a
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



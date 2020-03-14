# Unreal Engine C++编程踩坑指南

1. Unreal生成的类中的`GENERATE_BODY()`不能移动其所在行，否则会使intellisense和clang分析工具报错
2. 一定要在`GENERATE_BODY()`之后起两个空行再定于成员函数，否则会使intellisense和clang分析工具报错
3. 解决`GEngine`未定义: `#include "FirstPersonDemoGameModeBase.h"`
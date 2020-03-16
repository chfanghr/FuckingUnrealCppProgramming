# 💩 Unreal Engine C++编程踩坑指南 💩 

1. 💩 Clion索引代码太慢了（i7-8550U，8线程用了20min左右），而且在编辑代码时有性能问题，影响速度（可能是👴电脑太差
2. 💩 VSCode完全没有索引迹象，intellisense疯狂报错，pass
3. 💩 Visual Studio害行，除了长得丑。我换了Jetbrains Mono字体和背景图片感觉好多了
4. 💩 Reshaper C++完全不行，整完你的VS就跟Clion一样了，一卡一卡的
5. 💩 自己造的轮子尽量**header only**，WIndows上的动态链接库处理起来比较麻烦
6. 💩 Unreal生成的类中的`GENERATE_BODY()`不能移动其所在行，否则会使intellisense和clang分析工具报错
7. 💩 一定要在`GENERATE_BODY()`之后起两个空行再定义成员函数，否则会使intellisense和clang分析工具报错
8. 💩 解决`GEngine`未定义: `#include "Runtime/Engine/Classes/Engine/Engine.h"`
9. 💩 ~~使用c++17：在`$PROJECT/Source/$PROJECT/$PROJECT(Editor).Target.cs`的类构造函数中加入`CppStandard = CppStandardVersion.Cpp17`~~(自己的轮子里面用了std::optioanl和std::any)
10. 💩 用你妈的C++17，，，，，滚回去用C++11去了
11. 💩 在Windows下构建测试（GTest，conan，cmake，VS2019）：`cmake.exe -G "Visual Studio 16 2019" -DCMAKE_BUILD_TYPE=Release -DBUILD_TESTS=1 --config Release -DBUILD_EXAMPLES=1 -A x64 -DCMAKE_CONFIGURATION_TYPES=Release ..`
12. 💩 通过写插件来导入轮子。注意头文件路径不光在插件的构建脚本要写，工程的也要。
13. 💩 `std::string`转`TCHAR*`：`UTF8_TO_TCHAR(str.cstr())`
14. 💩 cmake在Windows用msvc构建32位库：`cmake.exe -G "Visual Studio 16 2019" -DCMAKE_BUILD_TYPE=Release --config Release -DCMAKE_CONFIGURATION_TYPES=Release -A Win32 -B "build32" ..`

**TODO**
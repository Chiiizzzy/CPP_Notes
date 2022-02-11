# 进入C++
## 大小写/拼写敏感
C++对于大小写和拼写敏感，例如我们`cout`生成字符输出，我们不能替换为`COUT`,`Cout`或者`kout`等。
## 保留程序运行窗口
C++在某些环境中会在独立的窗口中运行程序，并在运行完成后自动关闭窗口，如果想保留运行窗口直到用户键入任何键，我们需要在`return`语句之前添加`cin.get()`。
## C++的输入输出
C++同样可以使用`printf`以及`scanf`实现输入输出，但是需要包含常规C语言的头文件`stdio.h`。
## 一个C++程序示例及分析
```CPP
#include <iostream>
int main(char* name)
{
    /*
    This is a simple example.
    */
	using namespace std;
    // Display a greeting message.
	cout << "Hello " << name << endl;
	return 0; // Return 0 means the function is successfully executed.
}
```
上述代码实现了一个名为`main`的函数，这几行也被叫做函数定义（function defination），函数定义由两部分组成，第一行`int main()`叫函数头，花括号之间的部分叫函数体。
### 头文件
`#include`指定了本文件所依赖的C++头文件，例如我们要使用C++的输入输出工具，那么我们就需要include `iostream`这一头文件。我们在[上一章](../Chapter_1/1-4程序创建和编译.md)中提到过`#include`在与编译阶段就指进行处理，将`iostream`头文件的内容添加到程序中。具体的实现是由`iostream`文件的的内容将替代`#include`语句与源代码文件组成一个复合文件发送给编译器。
### 函数头
函数头定义了函数和程序其他部分的接口，本例中的`int`指的是函数的返回值是`int`类型，事实上`main`函数的返回值必须是`int`；`main`是函数名，其他程序通过函数名和参数来调用某个特定的函数；两个括号之间应该存放参数，本例中的`main`函数接受一个char的指针作为参数，实际上就是接收一个string作为参数。
### 函数体
函数体是指定函数做什么的指令，每一条完整的指令都叫做语句，每一条语句都要以`;`结尾。
### 注释
C++中的注释以`\\`开头或者以`\**\`包围，前者用于单行注释，后者用于多行注释。单行注释可以单独占据一行用于解释下方的代码块，也可以跟在代码后解释本行代码。
### 命名空间
`using namespace std;`这一条语句声明了本文件要使用的一个命名空间，支持命名空间是C++的一项特性，不同厂商可以将自己的代码打包在一个命名空间中，当我们利用`using namepsace std;`指令指定std命名空间时，就使得std命名空间内部的所有名称都变得更可用，比如`cin`和`cout`。但这一方式其实是一种偷懒的方式，并不被鼓励。当我们编写大型项目时，极有可能出现需要不同命名空间的名称的情况。所以我们一般仅用using声明需要的名称，或者干脆在需要使用的名称前加上命名空间：
```CPP
// Making cout, cin, endl available.
using std::cout;
using std::endl;
using std::cin;

// Clarify namespace before the cin, cout, endl.
sdt::cout << "hello wordl" << std::endl;
```
## 使用cout进行输出

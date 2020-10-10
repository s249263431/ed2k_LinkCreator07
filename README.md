# ed2k_LinkCreator07

1,源代码来自电驴官网，原版采用vs2003编译，新版本采用vs2019，多字节。没有屏蔽任何编译器警告。
2，FileHasher.cpp中用到了结构体FILE，这个结构体在vs2003和vs2019中定义是不同的。具体内容可以参考微软官方说明https://docs.microsoft.com/en-us/cpp/porting/visual-cpp-change-history-2003-2015?view=vs-2019 ，但是为了尊重历史，我定义了一个变量fd来存储文件描述符，同时使用函数fileno以FILE * 类型的指针file做参数来获取fd，函数_filelengthi64需要fd做参数。这就是全部的核心改变。
因为Visual C++ 2003 - 2015的巨大改变，原有的代码是无法通过编译的。
3，以前编译代码，总会觉得这里不好，那里不妥，现在学会了兼容， 学会了尊重历史。这也是人们进步的动力。随着编译器技术的发展，有些代码确实应该被淘汰。
4. LinkCreator32.exe  是一个支持批量计算ed2k的工具，计算结果自动保存在d:/myed2k.txt
5.支持计算完成之后自动关机。

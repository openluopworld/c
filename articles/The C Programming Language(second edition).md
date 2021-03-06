# C程序设计语言

#Chapter1
0) The size of a data type(int, short, long, double.) has relation to the machine.<br>
1) printf打印<br>
&nbsp;&nbsp;&nbsp;&nbsp;%d,按照十进制整数打印<br>
&nbsp;&nbsp;&nbsp;&nbsp;%ld,long int<br>
&nbsp;&nbsp;&nbsp;&nbsp;%6d,按照十进制整数打印，<b>至少</b>6个字符宽<br>
&nbsp;&nbsp;&nbsp;&nbsp;%f,按照浮点数打印<br>
&nbsp;&nbsp;&nbsp;&nbsp;%6f,按照浮点数打印，至少6个字符宽<br>
&nbsp;&nbsp;&nbsp;&nbsp;%.2f,按照浮点数打印，小数点后有两位小数<br>
&nbsp;&nbsp;&nbsp;&nbsp;%6.2f,按照浮点数打印，至少6个字符宽，小数点后有两位小数<br>
&nbsp;&nbsp;&nbsp;&nbsp;%g, print double value. From book C Traps And PitFalls.
&nbsp;&nbsp;&nbsp;&nbsp;%o,八进制数<br>
&nbsp;&nbsp;&nbsp;&nbsp;%x,十六进制数<br>
&nbsp;&nbsp;&nbsp;&nbsp;%c,字符<br>
&nbsp;&nbsp;&nbsp;&nbsp;%s,字符串<br>
&nbsp;&nbsp;&nbsp;&nbsp;%%,百分号本身<br>
2) EOF<br>
&nbsp;&nbsp;&nbsp;&nbsp;value of EOF is -1<br>
&nbsp;&nbsp;&nbsp;&nbsp;EOF is NOT:<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;a) A char<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;b) A value that exists at the end of a file<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;c) A value that could exist in the middle of a file<br>
&nbsp;&nbsp;&nbsp;&nbsp;<b>EOF is a macro defined as an int with a negative value. It is normally returned by functions that perform read operations to denote either an error or end of input.</b><br>

#Chapter2
1) int, short, long<br>
&nbsp;&nbsp;&nbsp;&nbsp;short与long两个限定符的引入可以为我们提供满足实际需要的不同长度的整型数。int通常代表特定机器中整数的自然长度。short类型通常为16位,long类型通常为32位，int类型可以是16位或32位。各编译器可以根据硬件特征自主选择合适的类型长度，但要遵循下列限制：short与int类型至少为16位，而long类型至少为32位，并且short类型不得长于int类型，而int类型不得长于long类型。<br>
2) 字符常量与仅包含一个字符的字符串之间的区别：'x'与"x"是不同的，前者是一个整数，其值是字母x在机器字符集中对应的数值（内部表示值）；后者是一个包含一个字符x以及一个结束符'\0'的字符数组。<br>
3) 库函数sqrt的参数为double类型，如果处理不当，结果可能会无意义（sqrt在<math.h>中声明。）因此，如果n是整数，可以使用sqrt((double)n)，类似的还有pow((double)x, (double)y)等;<br>
4) <b>static</b><br>
&nbsp;&nbsp;&nbsp;&nbsp;<b>外部的static声明通常多用于变量，当然，它也可以用于声明函数,static作用于外部变量和函数时都会将其可见性限制在本文件内。通常情况下，函数名字是可以全局访问的，对整个程序的各个部分而言都可见。但是，如果把函数声明为static类型，则该函数除了对该函数声明所在的文件可见外，其他文件都无法访问。</b><br>
&nbsp;&nbsp;&nbsp;&nbsp;static<b>也可用于声明内部变量。static类型的内部变量同局部变量一样，是某个特定函数的局部变量，只能在该函数中使用，但它与自动变量不同的是，不管其所在函数是否被调用，它一直存在，而不像自动变量那样，随着所在函数的被调用和退出而存在和消失。换句话说，static类型的内部变量是一种只能在某个特定函数中使用但一直占据存储空间的变量。每次调用对变量的修改对下次调用都是可见的。</b><br>

#Chapter5
1) 指针声明方式<b>int *p;</b>, 取值运算符*紧跟变量名。对于<b>int *p, q;</b>，p是一个指针变量，而q只是一个整形变量，写为int* p, q;容易产生误解。<br>
2) char message[] = "now"; the value of <b>sizeof(message)</b> is 4.<br>
3) The value of char <b>'\0'</b> is 0.<br>
4) 指针数组最频繁的用处是存放具有不同长度的字符串。<br>
5) <a href="http://c.biancheng.net/cpp/html/476.html" target="_blank">指针数组(int *a[10])：首先它是一个数组，数组的元素都是指针，数组占多少个字节由数组本身决定。它是“储存指针的数组”的简称。数组指针(int (*a)[10])：首先它是一个指针，它指向一个数组。在32 位系统下永远是占4 个字节，至于它指向的数组占多少字节，不知道。它是“指向数组的指针”的简称.</a><br>

#Ref
[1] <a href="http://www.ruanyifeng.com/blog/2011/11/eof.html">EOF</a><br>
[2] <a href="http://www.cnblogs.com/stoneJin/archive/2011/09/21/2183313.html">static作用（修饰函数、局部变量、全局变量）</a><br>

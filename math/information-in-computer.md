信息存储
========

<ol>
<li><span>计算机数据存储单位</span></a></li>
<li><span>进制转换</span></a>
<ul>
<li><span>常见的进制转换</span></a></li>
<li><span>二进制简介</span></a></li>
<li><span>进制计算的基本概念</span></a>
<ul>
<li><span>七进制计算</span></a></li>
<li><span>六十进制计算</span></a></li>
<li><span>十进制计算</span></a></li>
<li><span>进制计算的规律与公式推导</span></a></li>
</ul>
</li>
<li><span>二进制与十进制的转换</span></a>
<ul>
<li><span>二进制转十进制</span></a></li>
<li><span>十进制转二进制</span></a>
<ul>
<li><span>六十进制中</span></a></li>
<li><span>十进制中</span></a></li>
<li><span>除二取余法原理</span></a></li>
</ul>
</li>
</ul>
</li>
<li><span>二进制与十六进制的转换</span></a></li>
<li><span>大端法与小端法机器</span></a></li>
</ul>
</li>
<li><span>数字与编码</span></a>
<ul>
<li><span>ASCII编码</span></a></li>
<li><span>数字的计算</span></a></li>
<li><span>计算机中的数字与编码对比</span></a></li>
</ul>
</li>
</ol>


计算机数据存储单位
--------------------------------
<pre>
1TB (Trillionbyte 万亿字节 太字节 )     = 1024 GB
1GB (  Gigabyte   吉字节 又称“千兆” ) = 1024 MB
1MB (  Megabyte   兆字节 简称“兆” )   = 1024 KB
1KB (  Kilobyte   千字节 )              = 1024 B
1B  (    Byte     字节 )                =   8  Bit
</pre>

各位需要注意，内存上最小的单位是字节（byte）没有比这更小的单元了。而我们讨论的位（bit）是比字节还要小的单位，这个单位在计算机上是无法直接查看的（因为字节已经是最小的了），但是实际上而言计算机真正的所有数据都是有一个位一个位的1010之类的二进制数据组成的。而我们要进行C/C++编程的话，很多时候都需要去处理这个比内存最小单位还要小的位，如果是专做底层的话使用位操作就更加频繁了，所以我们必须要了【位级】也就是【二进制层面】的数据形式。

进制转换
--------------------------------


###常见的进制转换

生活中常见的进制：
}

我们的生活中充斥着各种各样的进制转换，例如每天工作生活的时候，可能很多人都不知道今天几号，但是却一定知道今天星期几，这个星期的概念中就存在着进制转换。满了七天就可以进一位变成一个星期，这是一个很常见的进制转换。

上述还列举了好几种其他的进制转换，我们可以很清晰的发现，其实不同的进制在【进位】的时候很明显的体现出一个规律便是：几进制就满几进一。


###二进制简介

那么实际上二进制跟上述常见的进制都是类似的，也就很简单的是满 2 进一位，我们可以看如下的式子：

<pre>
1 + 1 = 2
</pre>

这在我们十进制中是一个幼儿园的小孩子都懂的加法，但是到了二进制中这个结果会变得不一样了：

<pre>
1 + 1 = 10
</pre>

乍一看会觉得很难接受，但是仔细一想这也是可以理解的，因为在二进制中 满2 就会进一位，所以 1+1=2 已经满2了就进了一位结果就是 10 了。不过各位需要注意的是这个 10 是二进制中的 10 ：

<pre>
10(二进制) = 2(十进制)
</pre>

那么我们的二进制，再加几个数字看看:

<pre>
10 + 1 =  11 （等于十进制中的3）
11 + 1 = 100 （等于十进制中的4）
</pre>

情况就是这样，我们可以用这样的方式依次类推下来：

<pre>
二进制   十进制
    1       1
   10       2
   11       3
  100       4
  101       5
  110       6
  111       7
 1000       8
 1001       9
 1010      10
 1011      11
 1100      12
 1101      13
 1110      14
 1111      15
10000      16
</pre>

有些人可能会觉得奇怪，为了为什么这个看起来没有开始七进制那个星期的那样好理解，这里博主解释一下。

真正数学意义上的七进制里面是没有7的，因为到了6之后再加一 满 7 就要进一位变成 10 ，这个形式我们不是很熟悉但是换个熟悉的方式就理解了，因为我们平常生活着中把这个七进制的【个位】叫做【天】，【十位】叫做【星期】所以我们的七进制的：
<pre>
10 天
</pre>
也可以看做
<pre>
1星期 0天
</pre>




###进制计算的基本概念

首先我们要了解的是进制本身的一个概念：


####七进制计算

以星期的七进制举例：

<pre>
21
</pre>

这个值代表的天数到底是多少？我们将其换成我们所熟悉的单位一看：

<pre>
2 星期 1 天
</pre>

这样很直观的就能算出来 这个七进制的 21 所代表的的是十进制的 15 天，为什么呢？

很简单，因为一个星期是7天，所以上述的七进制数字转成十进制就是：

<pre>
7*2 + 1 = 15
</pre>


####六十进制计算

以时分秒的六十进制举例：

<pre>
356
</pre>

那么这个六十进制的 356 秒到底是十进制的多少秒？乍一看又有点晕了，不过没关系，换成我们所熟悉的单位来看看：

<pre>
3小时 5分钟 6秒
</pre>

这样看一下一下子就觉得简单了，我们也可以开始算了，答案就是：

<pre>
3*3600 + 5*60 + 6 = 11106（秒）
</pre>


####十进制计算

接下来我们再用十进制来举例：

十进制的：

<pre>
1234
</pre>

我想这个大家应该一眼就能看出来这个十进制的值，那么我们要看的是这个十进制的每一位拆开来看的式子：

<pre>
1*1000 + 2*100 + 3*10 + 4
</pre>



####进制计算的规律与公式推导

相信经过上面三种进制的举例之后，大家的心里已经模糊的有点想法，接下来我们就要把这个模糊的概念变的清晰。

首先我们定义一个未知数x（x>=2），那么假设我们所使用的这个进制是 x进制，那么这个 x进制有什么特点？

不用多说：

<pre>
① 满x进一
</pre>

相信大家可以理解

那么对于这个 x进制 的个位，单位的话一定 1，因为满了 x 就会进一位，所以由 ① 式可得：

<pre>
② 个位的最大值是 x-1
</pre>

那么各位同学想想，由 ①、② 式可以知道什么？那么博主也不卖关子：

<pre>
③ 第二位的 1 是第一位的 x 倍
</pre>

那么接下来的问题就是：

<pre>
x进制的 abcd （abdc 分别是0到x-1的数字） 等于 10进制的多少？
</pre>

大家可以停在这里先仔细考虑这个问题，当然草稿纸也是必要的，因为经过思考之后再来看博主的推理绝对会效果更佳！



那么，如果你已经思考过了我们就继续往下看。

由 第①、③式 就可以知道我们想要的结论了：

关于x进制的 abcd：

<pre>
个位数就是  d
十位数是   x*c
百位数是  x*x*b
千位数是 x*x*x*a
</pre>

所以最后答案是：

<pre>
④ 1111（x进制）= a*x^3 + b*x^2 + c*x^1 + d*x^0 （10进制）
</pre>

备注：

1. x^3 的意思就是 x的3次方 即 x*x*x

2. x^0 的意思是 x的0次方 即 1（除0以外，任意数的0次方都是1）


那么这个式子 ④ 是一个<font>通用形的公式</font>，可以计算任意进制转十进制。各位可以摊开草稿纸自行推导，以及套用求，博主这里就不废话了。


　


###二进制与十进制的转换


####二进制转十进制

既然有了公式，那么二进制转十进制自然是可以套用通用公式来计算的：

<pre>
例如 0100 1011 的十进制计算：

0100 1011(二进制) = 1*2^6 + 1*2^3 + 1*2^1 + 1*2^0 = 75 (十进制)
</pre>

或者使用 1248 法，那么什么是 1248 法，额，博主在写的时候才发现其实这个就是公式一种运用方式吧。就是记住2
的各个次方，依次从0次方开始分别是：1、2、4、8、16、32、64…… 等等

然后计算的时候碰到如下情况，直接套用：

<pre>
如 0001 0101 的十进制值计算：

0001 0101(二进制) = 16 + 4 + 1 = 21
</pre>

二进制的话，0就是没有值不用乘，1的话乘的时候可以省略，所以只要记住一些常见的 2 的次方就可以快速的将二进制转成十进制了。博主在视频当中二进制转十进制的时候就是这么做的 =v=

####十进制转二进制

使用【除二取余法】，例如：

<pre>
789(十进制) = 1100010101(二进制)

 789 / 2 = 商 394 余 1  个位
 394 / 2 = 商 197 余 0  十位
 197 / 2 = 商 98  余 1  百位
  98 / 2 = 商 49  余 0  第..位
  49 / 2 = 商 24  余 1  第..位
  24 / 2 = 商 12  余 0  第..位
  12 / 2 = 商 6   余 0  第..位
   6 / 2 = 商 3   余 0  倒数第3位
   3 / 2 = 商 1   余 1  倒数第2位
   1 / 2 = 商 0   余 1  倒数第1位
</pre>

那么我们的余数倒过来就是我们的二进制的值了。


#####六十进制中


11106 秒转 六十进制

<pre>
11106 / 60 = 商 185  余数 6
  185 / 60 = 商 3    余数 5
    3 / 60 = 商 0    余数 3 
</pre>

所以 11106 = 3小时 5分 6秒


#####十进制中


<pre>
1234 / 10 = 商 123 余 4
 123 / 10 = 商 12  余 3
  12 / 10 = 商 1   余 2
   1 / 10 = 商 0   余 1
</pre>



#####除二取余法原理



设两个未知数 x, y (x>=2) ，假设我们面对的是 x进制，要把十进制数 y 转成 x 进制

那么我们一定要清楚的是这个 y 去除以 x 能得到什么

假设这个 x进制的数是  abcd  (abcd为0~x之间常数) 当然这个x进制的数可能没有4位也可能超过4位，这没有关系我们只是看个示意，那么有了这个示例，根据我们最开始算出来公式可以得出下列等式：

<pre>
abcd(x进制) = a*x^3 + b*x^2 + c*x^1 + d*x^0 (十进制) = y 
</pre>

用这个数去除以 x 你会发现：

<pre>
y / x = ( a*x^3 + b*x^2 + c*x^1 + d*x^0 ) / x (十进制)
      = 商 a*x^2 + b*x^1 + c*x 余数 d
</pre>

那么获取的这个余数 d 就是我们 abcd 这个 x进制数的【个位】也就是第一位

<pre>
( a*x^2 + b*x^1 + c*x ) / x = 商 a*x^1 + b*x 余数 c
</pre>

再用这个商去除以 x 就能获得 x进制数的 第二位。依次类推，只要商不为0，我们就可以通过这个办法一直求下去。

各位可以用摊开草稿纸残念一下，也可以用这个结论反过来看看前几个 二进制、十进制、六十进制 用【除二取余法】的数据，博主就不赘述了，顺便感慨一下，百度百科上面那些进制转换的原理好残念，完全看不懂，不知道写着有什么意思。

　


###二进制与十六进制的转换


如果上面的公式你都有参与推倒，并且有使用公式进行过一定的转换联系，那么这个部分的内容对你而言肯定是小case

<pre>
 二进制   十六进制 十进制
0000 0000    00      0
0000 0001    01      1
0000 0010    02      2
0000 0011    03      3
0000 0100    04      4
0000 0101    05      5
0000 0110    06      6
0000 0111    07      7
0000 1000    08      8
0000 1001    09      9
0000 1010    0A      10
0000 1011    0B      11
0000 1100    0C      12
0000 1101    0D      13
0000 1110    0E      14
0000 1111    0F      15
0001 0000    10      16
0001 0001    11      17
0001 0010    12      18
0001 0011    13      19
0001 0100    14      20
0001 0101    15      21
0001 0110    16      22
0001 0111    17      23
0001 1000    18      24
0001 1001    19      25
0001 1010    1A      26
0001 1011    1B      27
0001 1100    1C      28
0001 1101    1D      29
0001 1110    1E      30
0001 1111    1F      31
0010 0000    20      32
</pre>

简单的观察一下就会发现上述二进制的低四位对应十六进制的第一位，上述二进制的高四位对应十六进制的第二位。

这其实是一个很简单的事情，因为【一】个【十六进制】的位刚好包含了【四】个【二进制】的位，这是因为十六进制的 x 是 16也就是 2的四次方，而二进制的 x 是 2 即 2的1次方。

我们通过观察上述数据也可以发现二进制的 0~1111 对应的刚好就是 十六进制的 0 ~ F 也就是二进制的四个位刚好对应一个十六进制的位。所以二进制与十六进制的转化十分简单：

<pre>
二进制   ：1111 0001 1010 0101 0111 1000
十六进制 ：   F    1    C    5    7    8
</pre>






###大端法与小端法机器

大端法和小端法，指的是数据的两种存储方式，对于一个数据 0x01234567 而言在

大端法机器上是

<pre>
      低 ------------------------> 高
内存地址：0x100 0x101 0x102 0x103
             01    23    45    67
</pre>

小端法机器上是

<pre>
      低 ------------------------> 高
内存地址：0x100 0x101 0x102 0x103
             67    45    23    01
</pre>

这是两种计算机存储字节数据的方式（2个十六进制的数表示8个二进制的位也就是1个字节）。大端法和小端法分别代表两种思想，一种是亲【人类直观】另一种是倾向【数学意义】

最开始看的时候会举得小端法有些不科学，其实这个是比较符合【数学意义】的，因为 67 是数字 0x01234567 中的个位与十位，是最低的一个字节，那么按照数学意义上来说的话，存储数据的时候从最低的字节开始写入是一种很正常的想法。只不过看起来不是那么直观。

而大端法的话，把最高字节的数据放在内存的低位其实就【数学意义】上看来是有些奇怪的，不过我们作为人看来却是比较亲切。

二者之间各有优点，各位只要了解即可，这个大小端只是做一个基础知识点。实际上编程时很少会感受到这中间的差别。

最后附上博主查看大小端的代码：


<source first>
#include <stdio.h>  // 包含 stdio 这个库的头文件

/*
 * main 函数 是程序的入口
 * 
 * int 是程序的返回值类型
 * main 是函数名
 * int argc 是参数个数
 * char const *argv[] 是指向参数的指针数组
 */
int main(int argc, char const *argv[])
{
  int i = 0x01234567;
  char *p;
  p = (char *)&i;

  printf("%x ", *(p+0));
  printf("%x ", *(p+1));
  printf("%x ", *(p+2));
  printf("%x ", *(p+3));

  // main 函数的返回值
  // return 是返回的关键字
  return 0;
}
</source>

由于大部分语法尚未开始讲解，所以这个程序的具体含义各位可以留待以后再来探讨。

数字与编码
--------------------------------

###ASCII编码

在数据的世界里, 实际上是没有任何中英文之类的字符. 所有的数据全都是1010之类的二进制组成的数字. 那么在这样的情况下, 我们要在计算机上使用字符就需要使用硬件上自带的编码才能把这些数字的数据编程我们所需要的文字等字符. 以下是使用范围最广的 ASCII 编码的一部分:

<table>
<tbody><tr>
<th> 二进制
</th>
<th> 十进制
</th>
<th> 十六进制
</th>
<th> 图形
</th></tr>
<tr>
<td> 0100&nbsp;0000 </td>
<td> 64
</td>
<td> 40 </td>
<td> <a>@</a>
</td></tr>
<tr>
<td> 0100&nbsp;0001 </td>
<td> 65
</td>
<td> 41 </td>
<td> A
</td></tr>
<tr>
<td> 0100&nbsp;0010 </td>
<td> 66
</td>
<td> 42 </td>
<td> B
</td></tr>
<tr>
<td> 0100&nbsp;0011 </td>
<td> 67
</td>
<td> 43 </td>
<td> C
</td></tr>
<tr>
<td> 0100&nbsp;0100 </td>
<td> 68
</td>
<td> 44 </td>
<td> D
</td></tr>
<tr>
<td> 0100&nbsp;0101 </td>
<td> 69
</td>
<td> 45 </td>
<td> E
</td></tr>
<tr>
<td> 0100&nbsp;0110 </td>
<td> 70
</td>
<td> 46 </td>
<td> F
</td></tr>
<tr>
<td> 0100&nbsp;0111 </td>
<td> 71
</td>
<td> 47 </td>
<td> G
</td></tr>
<tr>
<td> 0100&nbsp;1000 </td>
<td> 72
</td>
<td> 48 </td>
<td> H
</td></tr>
<tr>
<td> 0100&nbsp;1001 </td>
<td> 73
</td>
<td> 49 </td>
<td> I
</td></tr>
<tr>
<td> 0100&nbsp;1010 </td>
<td> 74
</td>
<td> 4A </td>
<td> J
</td></tr>
<tr>
<td> 0100&nbsp;1011 </td>
<td> 75
</td>
<td> 4B </td>
<td> K
</td></tr>
<tr>
<td> 0100&nbsp;1100 </td>
<td> 76
</td>
<td> 4C </td>
<td> L
</td></tr>
<tr>
<td> 0100&nbsp;1101 </td>
<td> 77
</td>
<td> 4D </td>
<td> M
</td></tr>
<tr>
<td> 0100&nbsp;1110 </td>
<td> 78
</td>
<td> 4E </td>
<td> N
</td></tr>
<tr>
<td> 0100&nbsp;1111 </td>
<td> 79
</td>
<td> 4F </td>
<td> O
</td></tr>
<tr>
<td> 0101&nbsp;0000 </td>
<td> 80
</td>
<td> 50 </td>
<td> P
</td></tr>
<tr>
<td> 0101&nbsp;0001 </td>
<td> 81
</td>
<td> 51 </td>
<td> Q
</td></tr>
<tr>
<td> 0101&nbsp;0010 </td>
<td> 82
</td>
<td> 52 </td>
<td> R
</td></tr>
<tr>
<td> 0101&nbsp;0011 </td>
<td> 83
</td>
<td> 53 </td>
<td> S
</td></tr>
<tr>
<td> 0101&nbsp;0100 </td>
<td> 84
</td>
<td> 54 </td>
<td> T
</td></tr>
<tr>
<td> 0101&nbsp;0101 </td>
<td> 85
</td>
<td> 55 </td>
<td> U
</td></tr>
<tr>
<td> 0101&nbsp;0110 </td>
<td> 86
</td>
<td> 56 </td>
<td> V
</td></tr>
<tr>
<td> 0101&nbsp;0111 </td>
<td> 87
</td>
<td> 57 </td>
<td> W
</td></tr>
<tr>
<td> 0101&nbsp;1000 </td>
<td> 88
</td>
<td> 58 </td>
<td> X
</td></tr>
<tr>
<td> 0101&nbsp;1001 </td>
<td> 89
</td>
<td> 59 </td>
<td> Y
</td></tr>
<tr>
<td> 0101&nbsp;1010 </td>
<td> 90
</td>
<td> 5A </td>
<td> Z
</td></tr>
<tr>
<td> 0101&nbsp;1011 </td>
<td> 91
</td>
<td> 5B </td>
<td> [
</td></tr>
<tr>
<td> 0101&nbsp;1100 </td>
<td> 92
</td>
<td> 5C </td>
<td> <a>\</a>
</td></tr>
<tr>
<td> 0101&nbsp;1101 </td>
<td> 93
</td>
<td> 5D </td>
<td> ]
</td></tr>
<tr>
<td> 0101&nbsp;1110 </td>
<td> 94
</td>
<td> 5E </td>
<td> ^
</td></tr>
<tr>
<td> 0101&nbsp;1111 </td>
<td> 95
</td>
<td> 5F </td>
<td> _
</td></tr></tbody></table>

<div></div>

完整请查看: http://zh.wikipedia.org/wiki/ASCII


ASCII（'''A'''merican '''S'''tandard '''C'''ode for '''I'''nformation '''I'''nterchange，'''美国信息交换标准代码'''）是基于拉丁字母的一套电脑编码系统, 它主要用于显示现代英语. 

对于 一个数字 65 如果我们告诉计算机我们要将其当做字符来使用, 那么这个数据就会被转换成对应的字符 '''A'''. 当然用 'A' 这样的字符也可以当做数字来计算, 因为虽然看起来它是个字符, 但实际上内存中只会存储 65 这个数字, 所以 'A' + 1 是可以计算的, 而且结果是 66, 转成字符就是 'B'.


###数字的计算

数字的计算跟平常数学意义上的计算没有太大的差别, 不过编程中的计算会有某些方便的拓展, 如位运算. 具体细节请参见后面的 CPU 计算章节.


###计算机中的数字与编码对比

在计算机当中, 所有的数据都是 1010 的二进制形式, 当你把这个数据当成是字符的时候, 计算机就会查找对应的编码, 当你把这个数据当成是图片时, 计算机就会按照对应的图片格式来加载这个数据. 如果仅仅是当做数字来计算的话, 那么就是普通的数学计算.

最开始学习编程基础的时候, 我们最需要了解的就是字符和数字的区别. 字符只是对应编码转换出来的一种符号, 如果编码不同的话字符转换出来的符号也可能不同, 所以并没有很强的数学意义. 而且在 C语言中 用于保存字符的 char 类型单位大小只有 1字节 也就说最多只有 255 种情况. 如果用字符来做计算的话也只能做一些简单的计算, 超过范围的话就会因为单位过小而无法保存运算的结果.

而在 C语言中 有 int 类型专门用于做整数的计算, 在 32 位操作系统上 int

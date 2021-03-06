#### 2.1 语法和语义的区别在哪里？

计算机语言的形式称为语法，其意义称为语义。语法侧重的是如何描述程序设计语言的结构规则。

#### 2.2 什么是 Kleene 星号？

正则表达式中的一个规则，可以指代上一个字符的任意次重复。

#### 2.3 正则表达式的 3 个基本操作是哪 3 个？

拼接、选择，和 Kleene 星号。

#### 2.4 上下文无关文法提供的额外操作是什么？

递归定义。

#### 2.5 什么是 Backus-Naur 形式？它是什么时候为了什么而发明的？

上下文无关文法的记法形式有时被称为 Backus-Naur（BNF），以彰显 John Backus 和 Peter Naur 的贡献，他们为了定义 Algol 60 语言而设计了这种形式。

#### 2.6 提出一种语言，缩进形式影响程序的语法。

Python

#### 2.7 讨论上下文无关文法时，什么是推导？什么是句型？

从一个开始符号导出一个非终结符的串，称为一个推导。推导过程中得到的各个符号串称为句型。

#### 2.8 最左推导与最右推导的区别在哪里？哪一个被称为规范推导？

最右推导是指，在推导的过程中，每一步都用某个产生式的右部代换掉位置在最右的非终结符。而最左推导是指，每一步都用某个产生式的左部代换掉位置在最左的非终结符。

其中最右推导称为规范推导。

#### 2.9 一个上下文无关文法有歧义是指什么意思？

指一个串可以生成多于一个语法分析树。

#### 2.10 为什么扫描器必须保存单词的正文？

扫描器把输入字符结成单词，这样可以显著减少输入个体的数量，是需要检查他们的计算量更大的语法分析程序更方便。

#### 2.11 什么是编译指示（pragma）？

编译指示是指语言实现提供的一些特定的有意义的注释。它们不影响程序的语义，但是会影响程序的编译过程。

#### 2.12 为什么有时扫描器需要“前窥”下一个字符？

简单的原因是，一些合法单词同时也是另外某个单词的合法前缀，“最大可能单词”规则要求我们在这时继续向前扫描。

更复杂的原因是在一些语言中（如 Fortran），空格是被忽略的东西，包括出现在变量名字中间的空格。因此扫描器需要向前窥探一定的深度，才能知道当前的单词是否结束。

#### 2.13 什么是结合性和优先级？

结合性指的是在优先级相同的情况下，应该以什么顺序对运算对象进行运算符操作；
优先级指的是在默认运算顺序下，优先的运算符可以提前对运算对象进行操作。

#### 2.14 请总结一下 LL 和 LR 分析之间的差异，它们中的哪一个又被称为 “自上而下”？哪一个是“自下而上”？哪一个又被称为“预测性”的或者“移入-归约”的？“LL”和“LR“各表示什么？

LL 表示“从左向右，最左推导”，也被称为“自上而下”或“预测性”分析器；LR 表示“从左到右，最右推导”，也被称为“自下而上”或“移入-归约”分析器。

#### 2.15 哪一类语法分析器在产品编译器中使用最普遍？

LR 语法分析器。

#### 2.16 yacc/bison 生成的是哪一类语法分析器？

属于LR语法分析器。

#### 2.17 与手工写出的扫描器相比，自动生成的扫描器有哪些优势？为什么大部分产品编译器还是采用手工写的扫描器？为什么他们不用手工写出的语法分析器？

自动生成的扫描器由于借助正则表达式，因此特别容易书写与修改。大部分产品编译器还是采用手写的扫描器是出于性能方面的考虑。

手写的语法分析器指的是递归下降式语法分析器，生成器的语法分析器指的是表格驱动式分析器。不用手写的语法分析器原因还不太懂，只知道递归下降语法分析器常常用于分析哪些相对容易分析的语言，或在没有可用的分析器生成工具时使用。

#### 2.18 什么是 FIRST 和 FOLLOW 集合？他们有什么用处？
FIRST 和 FOLLOW 集合常用于表示产生式的最开头与结尾的串的集合。这种形式可用在递归下降式中写 case 分支的标号，具有预测性的作用。

#### 2.19 请描述两种情况，其中上下文特定的 FOLLOW 集合可能有用。
不懂。

#### 2.20 请说明两种常见的不能通过自上而下的方式的上下文无关语法形式

左递归和公共前缀。

#### 2.21 什么是“悬空的else”问题？新语言里怎么避免这一问题？

悬空的else 问题是指，使用 if then else 文法的语言出现两个或两个以上嵌套的条件语句时，无法判断当中的 else 应该与哪个 if 相配对，出现歧义。

新语言里通过将 else if 改写成 elif ，并添加 end 语句指明 if 的边界，从而避免歧义。

#### 2.22 请解释 LR 语法分析中特征有穷自动机的意义。

不太懂。

#### 2.23 在一个 LR 项里的圆点有什么意义？

表示当前分析栈顶的位置。

#### 2.24 根据什么区分一个 LR 状态里的基础和闭包？

最初的项称为一个表的基础，后面加入的项是它的闭包。

#### 2.25 一个右句型的句柄是什么？

在最右推导分析的每一步，需要结合到一起的那些符号都表示下一步的反向推导，称他们为这个句型的句柄。 


有很多方法. 最简单的是: 
:s/old/new/g, 但是,这仅对当前行起作用..., 所以,我们用 
:%s/old/new/g, 更一般的,我们还可以用 
:s/old/new/,这里,是任意的行范围,包括行号,$(文件末尾),.(当前行) 
%(当前文件),或者两个行号之间加个破折号(或者可以这样: ., 5,这表示下面5行).是 
c,g,i中间的一个或者什么也没有.
c告诉vi每次替换的时候要给提示,
g是说对所有一行中出的地方都做替换.
i则是指在查找时不区分大小写.如果最后一个斜杠(/)后面没有东西的话,
么vi只替换在行中第一次匹配的地方. 
我比较喜欢这样做: 
:g/foobar/s/bar/baz/g, 这个命令首先搜寻foobar,然后把它变成foobaz. 它没有改变 
jailbars, 而其他的一些命令可能会改变jailbars. 这是我的方法,但是可能比较难记. 
当然,你还可以在查找的的时候使用正规式,以及在替换文本的时候使用其他一些命令.如?
你在正规式里用(和)来剥离一个序列的话,你会发现你可以做很多好玩的事情. 
例如: 
:g/(foo)(bar)/s/2/1baz/g 将foobar替换成foobaz 
还有一些特殊的序列: 
& 所有查找时匹配到的东西 
1到9号用(和)括起来的东西 
u 下一个字符将被变成大写. 
U 以后的字符都变成大写,直到遇到e或E 
l 下一个字符将被变成小写. 
L 以后的字符都变成大写,直到遇到e或E 
更改大小写的选择区域的终点 



set fileformat=unix



插入递增序列
:%s/\%9c./\=line(".")/g


:set statusline=%<%f\ %h%m%r%=%-14.(%l,%c%V%)\ %P
CTRL-B/CTRL-E 可以用来跳转到命令行的开始和结束位置。

6 modes in intro.cnx

edit binary files(*.o;*.exe)
1. 用vim -b 打开文件
2. 使用:%!xxd命令
3. 编辑文件（只编辑右边字符不会保存）后使用:%xxd -r

898
|;|	N  ;		重复上次 "f"、"F"、"t" 或 "T" 命令 N 次
|,|	N  ,		以相反方向重复上次 "f"、"F"、"t" 或 "T" 命令 N 次
|[(|	N  [(		向后至第 N 个未闭合的 '('
|[{|	N  [{		向后至第 N 个未闭合的 '{'

|])|	N  ])		向前至第 N 个未闭合的 ')'
|]}|	N  ]}		向前至第 N 个未闭合的 '}'

|[#|	N  [#		向后至第 N 个未闭合的 "#if" 或 "#else"
|]#|	N  ]#		向前至第 N 个未闭合的 "#else" 或 "#endif"

|gd|	   gd		至光标下标识符的局部声明 (goto declaration)
|gD|	   gD		至光标下标识符的全局声明 (goto Declaration)

|`.|	   `.		至当前文件最后被改动的位置
|:ju|	  :ju[mps]	列出跳转表

CTRL-O(ou) {command}  执行命令 {command} 并回到插入模式 
|i_CTRL-W|	CTRL-W		  删除光标前的一个单词
|i_CTRL-U|	CTRL-U		  删除当前行的所有字符
|i_CTRL-R|	CTRL-R {0-9a-z%#:.-="}	插入寄存器的内容
|:r|	   :r [file]	   将文件 [file] 的内容插入到光标之下
|:r!|	   :r! {command}   将命令 {command}  的标准输出插入到光标之下

|quote|	  "{char}	在接下来的删除、抽出或放置命令中使用寄存器 {char}
|:reg|	  :reg		显示所有寄存器的内容
|:reg|	  :reg {arg}	显示寄存器 {arg} 的内容
|v_u|	     {visual}u	改高亮的文本为小写
|v_U|	     {visual}U	改高亮的文本为大写
|g~|	     g~{motion} 将动作 {motion} 覆盖的文本翻转大小写
|gu|	     gu{motion} 将动作 {motion} 覆盖的文本改为小写
|gU|	     gU{motion} 将动作 {motion} 覆盖的文本改为大写
|CTRL-A|  N  CTRL-A	将光标之上或之后的数值增加 N
|CTRL-X|  N  CTRL-X	将光标之上或之后的数值减少 N

By default, the :substitute command changes only the first occurrence on each line.
If you want to change every occurrence on the line, you need to add the g (global) flag.

CTRL-E Scroll one line up.
CTRL-Y Scroll one line down.
z+			Without [count]: Redraw with the line just below the
			window at the top of the window.  Put the cursor in
			that line, at the first non-blank in the line.
			With [count]: just like "z<CR>".

z^			Without [count]: Redraw with the line just above the
			window at the bottom of the window.  Put the cursor in
			that line, at the first non-blank in the line.
			With [count]: First scroll the text to put the [count]
			line at the bottom of the window, then redraw with the
			line which is now at the top of the window at the
			bottom of the window.  Put the cursor in that line, at
			the first non-blank in the line.



在模式里用 |/\c| 来忽
略大小写或 |/\C| 来匹配大小写。
如果没有 'g' 标志位，每行只加一次。
如果有 'g'，每个匹配都被加入。
如果有 'j'，只更新 quickfix 列表

有两条命令可用于在跳转到差异文所在的位置:
								*[c*
	[c		反向跳转至上一处更改的开始。计数前缀使之重复执行相应
			次。
								*]c*
	]c		正向跳转至下一个更改的开始。计数前缀使之重复执行相应
			次。

"for programmers
[CTRL-I, ]CTRL-I Search for a word under the cursor in the current file and any brought in by #include directives.
gd, gD Search for the definition of a variable.
]CTRL-D, [CTRL-D Jump to a macro definition.
]d, [d, ]D, [D Display macro definitions.

The % command is designed to match pairs of (), {}, or [].

CTRL-D Macro definitions
CTRL-F Filenames
CTRL-K Dictionary
CTRL-I Current files and #included files
CTRL-L Whole lines
CTRL-] Tags
CTRL-P Same as CTRL-P without the CTRL-X (find previous match)
CTRL-N Same as CTRL-N without the CTRL-X (find next match)


vim ftp://adah@server/temp/test.cpp

vim -d file1.txt file2.txt 可以用比较模式查看编辑两个文件


c-p(c-n)        在编辑模式中, 输入几个字符后再输入此命令则 vi 开始向上(下)搜
                  索开头与其匹配的单词并补齐, 不断输入此命令则循环查找. 此命令
                  会在所有在这个 vim 程序中打开的文件中进行匹配.
  c-x-l           在编辑模式中, 此命令快速补齐整行内容, 但是仅在本窗口中出现的
                  文档中进行匹配.
  c-x-f           在编辑模式中, 这个命令表示补齐文件名. 如输入:
                  /usr/local/tom 后再输入此命令则它会自动匹配出:
                  /usr/local/tomcat/
  abbr            即缩写. 这是一个宏操作, 可以在编辑模式中用一个缩写代替另一个
                  字符串. 比如编写java文件的常常输入 System.out.println, 这很
                  是麻烦, 所以应该用缩写来减少敲字. 可以这么做:
                  :abbr sprt System.out.println
                  以后在输入sprt后再输入其他非字母符号, 它就会自动扩展为System.
                  out.println

* 	查找光标所在处的单词，向下查找
# 	查找光标所在处的单词，向上查找

在前面加入 \c 表示忽略大小写
    /\celephant

 vim -d file1.txt file2.txt 可以用比较模式查看编辑两个文件

软件名字段的特征是：位于行首；由若干个单词组成，单词之间用一个空格分开。
    ^\S\+\( \S\+\)*
编号字段的特征是：恰好六个数字。
    \<\d\{6}\>
价格字段的特征是：若干个数字，一个点，若干个数字。
    \d\+\.\d\+
开发者字段的特征跟软件名字段的特征类似，但是位于行末。
    \S\+\( \S\+\)*$


:%s/elephant/pig/g
    g 表示如果一行有多个 elephant 将全部替换，没有 g 表示只替换每行第一个。
    另外还有 i 标志，有 i 表示忽略大小写。

(1)快速查看你的头文件
头文件的一个性质是防止被重复引用，如test.h，常常在开头放上#ifndef _TEST_H...之类的
好了，现在你经常想查看stdio.h的头文件，这样的书写你的stdio.h头文件
#include <stdio.h> /* _STDIO_H */
把你的光标放在_STDIO_H上，按下control+w键后，在按下<tab>键，奇迹诞生了！
解释：control+w貌似一个搜索命令(好像跟打开窗口有关)，搜索光标所在的字符串，而_STDIO_H是stdio.h的特有的，按下<tab>于是就找
stdio.h了，哈哈
(2)快速加或减你的数字
光标放在你的数字上，按下control+a和control+x


扩展当前的文件名和目录名
cnoremap >fd <C-R>=expand('%:p:h').'/'<CR>
cnoremap >fn <C-R>=expand('%:p')<CR>
常用目录的缩写
cnoremap >v ~/.vim/
cnoremap >ftp ~/.vim/ftplugin/
cnoremap >tp ~/.vim/plugin/
cnoremap >rc $VIM/_vimrc
最好的东西放到最后来说:)
noremap <m-e> :e<space>
noremap <m-s-e> :e<space>**/*
noremap <m-s-n> :n<space>**/*

超赞上面这几个,原话这么说的:
The mapping **/* is used to find a file using glob pattern thus in any subdir.
:n is opening all matches. you can cycle through the matches using tab.
不必知道目录的结构,只要记得文件名的部分内容,就能找到所有匹配的文件

gvim -S Session.vim : 重新读取一个session，也就读取了所有文件,ft

Tlist 打开或者关闭当前文件的索引；
TlistSync 立即在打开的索引窗口中定位当前的光标所在位置属于哪个函数或者结构定义中。

在insert模式下，C-R (register) 插入register里的内容，一个有趣的reg是"=".
假设你想输入123K的具体字节数，不用打开计算器，试试这个“<C-R>=1024*123<CR>”，
“125952”就出来了！
另外在命令行里C-R C-W和C-R C-A是必用的技巧，它们将光标下的<word>和<WORD>
考到命令行里，省了你无数的typing。


使用 % 键可以查找匹配的括号。

使用 [{ 和 ]} 命令可以跳转到光标所在程序块的开头和结尾。

如果当前光标处的单词是一个局部变量，则使用 gd 来跳转到该变量的定义处；
如果当前光标处的单词是全局变量，则使用 gD 来跳转到该变量的定义处。


[i 命令可以快速察看光标所在位置的变量的定义，[d 命令可以快速察看光标所在位置的宏的定义。


在 vim 中使用 Ctrl-O 执行后退，使用 Ctrl-I 执行前进。
相关帮助：  :help CTRL-O  :help CTRL-I   :help jump-motions


进行一次搜索之后，执行 :nohlsearch 或 :noh 可以暂时关闭本次搜索结果的高亮显示。而使用 :set nohlsearch 则可以永久关闭搜索高亮显示。
可以将:noh命令映射到一个键上，例如:nmap <silent> <C-N> :silent noh<CR>，这样就可以使用Ctrl-N来关闭高亮显示。

使用 Ctrl-O 就可以临时切换到 normal mode, 执行一个命令后自动返回 insert mode。
于是上述命令序列可以改为：
Ctrl-O、fd 即可。
Ctrl-O 要按两个键呢，很麻烦，于是来个 keymap
" make ` functions <C-O> in insert mode
inoremap ` <C-O>
nnoremap ` i`<ESC>

在 normal mode 下按 ` (左上角那个)，会正常插入 `，
而在 insert mode 下则相当于按 Ctrl-O，
于是上述命令序列又可简化为
`fd 即可。
在 insert mode 想粘贴剪贴板内容时，可以输入 `P，爽吧？


:tag 命令那样方便地跳转



把光标所在行移动窗口的顶端、中间或底部，这时就可以用到”zt“、”zz“和”zb“





"CTRL-t" 就可以回到搜索前的位置。 

plugin/wintagexplorer.vim – winmanager提供的tag插件，用处不大

map <M-1> 1gt 将 alt+1 映射为 normal 模式下的 1gt 操作, 就是标签页的切换操作.
下面的同 <M-1>
<C-S>  ctrl+s 保存相当于命令行语句 :write
au BufWinLeave *.ztx mkview  自动保存试图设置.

":noremap" 命令可以用来输入不会被重映射的映射。这可以用来交换两个键的含义。
":cmap"、":cunmap" 和 ":cnoremap" 可以用来只在命令行编辑时映射。":imap"、
":iunmap" 和 ":inoremap" 则可用作插入模式的映射。类似的命令对缩写也存在:
":noreabbrev"、":iabbrev"、":cabbrev"、":iunabbrev"、":cunabbrev"、
":inoreabbrev"、":cnoreabbrev"。

"for minibufexplorer
用:bn或:bp即可在文件之间切换

~ 	切换大小写，当前字符
g~iw 	切换当前字的大小写
gUiw 	将当前字变成大写
guiw 	将当前字变成小写
>> 	将当前行右移一个单位
<< 	将当前行左移一个单位(一个tab符)
== 	自动缩进当前行

" Changing Case 
guu : lowercase line 将整行变成小写
gUU : uppercase line 
Vu : lowercase line 
VU : uppercase line 
g~~ : flip case line 小写变大写，大写变小写
vEU : Upper Case Word 
vE~ : Flip Case Word 
ggguG : lowercase entire file 将整个文件变小写

gui t/f


可视模式
标记文本
v 	进入可视模式，单字符模式
V 	进入可视模式，行模式
ctrl+v 	进入可视模式，列模式，类似于UE的列模式
o 	跳转光标到选中块的另一个端点
U 	将选中块中的内容转成大写
O 	跳转光标到块的另一个端点
aw 	选中一个字
ab 	选中括号中的所有内容，包括括号本身
aB 	选中{}括号中的所有内容
ib 	选中括号中的内容，不含括号
iB 	选中{}中的内容，不含{}

对标记进行动作
> 	块右移
< 	块左移
y 	复制块
d 	删除块
~ 	切换块中内容的大小写

cc 	删除当前行并进入编辑模式

gd 	跳至当前光标所在的变量的声明处

fx 	在当前行中找x字符，找到了就跳转至
tx 	与fx类似，但是只是跳转到x的前一个字符处
),( 	跳转到上/下一个语句


书签
ma 	把当前位置存成标签a
`a 	跳转到标签a处


gt 	切换到下一个标签页
gT 	切换到上一个标签页
:tabr 	切换到第一个标签页
:tabm [N] 	把当前tab移动到第N个tab之后

窗口命令

 
ctrl+w s 	水平分割窗口
ctrl+w w 	切换窗口
ctrl+w q 	退出当前窗口(由于同时有多个文件，此命令不会影响其他窗口)
ctrl+w v 	垂直分割窗口

:bn 	跳转到下一个缓冲区
:bd 	删除缓冲区(关闭文件)
:sp fn 	分割窗口，并将fn加载到新的窗口中

P 	粘贴粘贴板的内容到当前行的上面
]p 	有缩进的粘贴，vim会自动调节代码的缩进
"a 	将内容放入/存入a寄存器，可以支持多粘贴板

附：比如常用的一个寄存器就是系统寄存器，名称为+，所以从系统粘贴板粘贴到vim中的命令为"+p,注意此处的+不表示操作符，二十一个寄存器。



"fast saving
nmap <leader>x :xa!<cr>
nmap <leader>w :w!<cr>

"switch to current directory
map <leader>cd :cd %:p:h<cr>

" tag list --
map <F3> :Tlist<cr>

"remove the windows ^M windows系统中常常可以看到文本中夹杂着^M这样的控制字符，用此命令删除之
noremap <leader>m :%s/"r//g<cr>

" Changing Case 
guu : lowercase line 将整行变成小写
gUU : uppercase line 
Vu : lowercase line 
VU : uppercase line 
g~~ : flip case line 小写变大写，大写变小写
vEU : Upper Case Word 
vE~ : Flip Case Word 
ggguG : lowercase entire file 将整个文件变小写


map命令提供给用户自定义键绑定的功能，这使得vim变成了一个高度可定制的编辑系统。比如你在别的编辑器中习惯使用CTRL+S进行保存，在vim中默认的行为是 :w，你可能觉得不顺手，那么就可以将保存文件的命令进行mapping

imap <CTRL-S> :w<CR>
其中i表示在插入模式。

我比较喜欢使用Function键作为快捷键，比如：
imap <F7> <ESC>:w!<cr>
imap <F8> <ESC>:w!<cr>i

= 自动缩进
ctrl+p 自动补全
 

下移n行 nj
上移n行 nk 




命令:mkv!，即可自动保存当前的所有配置到.vimrc

17gg 跳到第17行；

12| 跳到当前行的第12个字符；
8l 右移8个字符，结合gg可以快速定位错误的位置；

ggvG 全选

= 自动缩进当前行；
gg=G 自动缩进整个文本；
=a{ 自动缩进{}内的文本；
= 自动缩进当前行；
gg=G 自动缩进整个文本；
=a{ 自动缩进{}内的文本；

如果光标目前在一个字符串的第一个引号上，”blah blah blah”，要删除引号中的内容，就d/”+enter，对删除括号中的内容同理如果光标目前在一个字符串的第一个引号上，”blah blah blah”，要删除引号中的内容，就d/”+enter，对删除括号中的内容同理

到 函数名上,按“K”(大写的 K),直接就会跳到 Linux 程序员手册


:scriptnames(or version)   发现配置文件的位置
vim -x exam.txt "加密文件exam.txt"
:setlocal noswapfile "可在编辑过程中禁止使用交换文件"
:buffers 或:ls "列出整个缓冲区列表,"
:%s/\s\+$//   "消除所有行尾的多余空格"
:syntax enable "打开色彩"

:tabe filename
:tabn num
:tabp
:tabc
:tab help gt

~ 切换字符的大小写 
. 重复上一个操作 
:e <文件> 不离开vi编辑<文件> 
:e! 放弃所有修改，从上次保存文件开始再编辑

你可能常常会重复同样的错误，你的手指所做的并非是你要它做的。可以使用缩写(abbreviation)进行修正。下面是一些例子：

* :abbr Lunix Linux
* :abbr accross across
* :abbr hte the
这些词会在编辑时被自动改正。

调出历史命令用q:

如果你看到一个特定词，想看看其他地方是不是出现过同样的词，可以使用*命令。它将对光标所指的词进行搜寻。

:.=                      打印当前行的行号
:=                       打印文件中的行数
^g(Ctl + g)           显示文件名、当前的行号、文件的总行数和文件位置的百分比

m(a-z)                   用一个字母来标记当前位置，如用mz表示标记z
'(a-z)                   将光标移动到指定的标记，如用'z表示移动到z




:map key command_seq     定义一个键来运行command_seq，如:map e ea，无论什么时候都可以e移到一个字的末尾来追加文本
:map                     在状态行显示所有已定义的宏
:umap key                删除该键的宏

:ab string1 string2      定义一个缩写，使得当插入string1时，用string2替换string1。当要插入文本时，键入string1然后按Esc键，系统就插入了string2
:ab                      显示所有缩写
:una string              取消string的缩写

:set ai                  打开自动缩进

n<<                      使n行都向左移动一个宽度
n>>                      使n行都向右移动一个宽度，例如3>>就将接下来的三行每行都向右移动一个移动宽度




z(回车)                 将当前行置为屏幕的顶行
nz(回车)                将当前行下的第n行置为屏幕的顶行
z.                       将当前行置为屏幕的中央
nz.                      将当前行上的第n行置为屏幕的中央
z-                       将当前行置为屏幕的底行
nz-                      将当前行上的第n行置为屏幕的底行


.                        重复最后一次修改
,                        以相反的方向重复前面的f、F、t或T查找命令





:[范围]s/[A-Z]/l&/g   改小写

:g/text1/s/text2/text3   查找包含text1的行，用text3替换text2


:set ic                  查找时忽略大小写
:set noic                查找时对大小写敏感
&                        重复最后的:s命令


yy                       将当前行的内容放入临时缓冲区
nyy                      将n行的内容放入临时缓冲区
p                        将临时缓冲区中的文本放入光标后
P                        将临时缓冲区中的文本放入光标前



vi + filename: 打开文件，并将光标置于最后一行首 
vi +/pattern filename: 打开文件，并将光标置于第一个与pattern匹配的串处 
vi +n [filename] ：打开文件，并将光标置于第n行首
vi +/pattern [filename]：打开文件，并将光标置于第一个与pattern匹配的串处







A 在当前行的末尾添加 
（I 在行首添加？）

w 下一个单词的开头 
W 下一个单词的开头,忽略标点符号 

B 上一个单词的开头,忽略标点符号 

自动转到插入模式
c 覆盖... 
C 覆盖到行末尾 

仍为命令模式
d 删除... 
D 删除到行末尾 

自动转到插入模式
s 替换 
S 替换整行 


E 单词的末尾,忽略标点符号

G ...跳至[缺省是到文件末尾] 


nH                       将光标移动到屏幕顶行下的第n行
nL                       将光标移动到屏幕底行上的第n行

f 查找... 
F 向后查找... 


J 把下一行合并到本行 
nJ 连接后面n行


N 逆向重复上次查找 


p 
(译注--应为在当前位置的后面粘贴) 
P 
(译注--应为在当前位置的前面粘贴) 



ttext                     在当前行向前查找text，并将光标定位在text的第一个字符
Ttext                    在当前行向后查找text，并将光标定位在text的第一个字符


X   删除前一个字符 
nX 从当前光标处往前删除n个字符
ndw 从当前光标处往后删除n个字
ndd  从当前行开始往后删除


y 复制... 
Y 复制整行 



+ 下一行的开头 
- 上一行的开头 

n+: 光标下移n行 
n-: 光标上移n行 



n$: 光标下移n行至行尾 

H: 光标移至屏幕顶行 
M: 光标移至屏幕中间行 
L: 光标移至屏幕最后行 

0: 光标移至当前行首 
$: 光标移至当前行尾 

Ctrl+u: 向文件首翻半屏 
Ctrl+d: 向文件尾翻半屏 

Ctrl+f: 向文件尾翻一屏 
Ctrl＋b: 向文件首翻一屏 


用 vi 多行注释

如果要给多行程序作注释，一个笨办法就是 插入 # ，然后用 j 跳到下一行用 . 命令， 
重复上个命令。如果要注释几百行，这样的方法恐怕太愚蠢了。一个聪明的办法是： 

:.,+499 s/^/#/g  



i: 在光标前 
a: 光标后 

I: 在当前行首 
A: 在当前行尾 

dG 删除行，直到文件结束
d0: 删至行首 
d$: 删至行尾 
（D也可以）
db                       删除光标前面的字
ndb                      从当前行开始往前删除n字



:n,md            从第m行开始往前删除n行


ndd: 删除当前行及其后n-1行 


cw text escape            将当前字改为text

C text escape             将当前行余下的改为text
cG escape                修改至文件的末尾


ZQ（无条件退出） //vi 没用，vim可能有用
ZZ（存盘退出）

查找和替换

:[范围]s/old/new/[cgi],这里,[范围]是任意的行范围,包括行号,$(文件末尾),.(当前行), %(当前文件),或者两个行号之间加个破折号(或者可以这样: .,+5,这表示下面5行).

:g/\(foo\)\(bar\)/s/\2/\1baz/g 将foobar替换成foobaz 
还有一些特殊的序列: 
& 所有查找时匹配到的东西 
\[1-9] 1到9号用\(和\)括起来的东西 
\u 下一个字符将被变成大写. 
\U 以后的字符都变成大写,直到遇到\e或\E 
\l 下一个字符将被变成小写. 
\L 以后的字符都变成大写,直到遇到\e或\E 
\[Ee] 更改大小写的选择区域的终点 

c告诉vi每次替换的时候要给提示
g是说对所有一行中出现的地方都做替换
i则是指在查找时不区分大小写.

:s/p1/p2/g: 将当前行中所有p1均用p2替代
:#,#s/old/new/g: 在两行内替换所有的字符串 old 为新的字符串 new
:n1,n2s/p1/p2/g: 将第n1至n2行中所有p1均用p2替代
:g/p1/s//p2/g: 将文件中所有p1均用p2替换


:s/p1/p2/g: 将当前行中所有p1均用p2替代

下面两种替换都可以生效。
 :%s/old_word/new_word/g
这个指令是于在整个文件中替换特定字符串  

:%s/the/THE
我们把整篇文档的所有的the都替换成THE


:n1,n2 co n3: 将n1行到n2行之间的内容拷贝到第n3行下
:n1,n2 m n3: 将n1行到n2行之间的内容移至到第n3行下
:n1,n2 d: 将 n1行到n2行之间的内容删除


%（跳转到与之匹配的括号处） 
.（重复上次的修改命令） 
`.（跳转到最近修改过的位置）



“pri”后面输入“Ctrl-P”

redo:Ctrl+r
undo:u

:set hlsearch

或是在~/.vimrc加上一行：
代码:
set hlsearch
如果不想要高亮了，就set nohlsearch
改成带颜色的
syntax on/syntax off
用法和上面那个一样。注意，确定用的是vim



/<文本>将向前查找, ?<文本>将向后查找. 
??或者//将重复上次查找. 在UNIX下,
n将查找文本下一次的出现位置. 
N重复上次查找, 不过逆转了查找的方向. 在查找中可以使用规范式. 



:e!可以不保存修改而重新把你的文件调进来. 

你删除的文本都保存在从0到9编号的寄存器里.所以,"<n>p就可以把上第n次的删除文本粘贴出来.你可以按如下的方法迅速地查看所有删除的文本. 先试一个,不对的话,敲u,再试下一个.(为加速这个过程, 这时vi中的.命令和通常的用法不一样了.它不是重复上次操作,而是试下一个寄存器,这样你要做的无非就是: "1p u . u .,直到你撤消了你想撤消的删除操作) 


:[m],[n]w <文件名>可以将从第m行到第n行之间的文本保存到<文件名>所指定的文件中. 
这种行序号方法几乎在所有的:命令下都可以使用. 

这时可以用   ctrl+6   的组合键在两个文件中切换。


如果你用命令:[m],[n] w >><文件名>, 这些文本将添加到文件的后面. 





:set ai可以让vi自动对齐. 
:set sw=#,#是移动的宽度(shiftwidth),或者说TAB键的宽度(tabwidth);你可以 
用<<或者>>命令来左移或右移某一行. 还有, 你可以使用 <%或>%来将{,(或[等符号 
括起来的文本都左移或右移;这时候,你必须把光标放在这些符号({,(或[)上面. 
:set sm会在你敲},]或)显示出对应匹配的{,[或(来. 
:set lisp会对lisp编程有些帮助. ()被移到s表达式(s-expressions)外面,如果 
原子(atoms)没有停止则{}将被移走. 

:ab email ellidz@midway.uchicago.edu 可以在你敲完email后,把那个没有缩写的文本插入到文件中. :una email取消缩写. 




xp 删除光标下的字符,再把粘贴到后面去.换句话说,它交换了当前两个字符的位置. 
ddp 和xp类似,不过是交换两行的位置. 
uu 撤消和重复上次所做的修改.(这可以使你不改变什么东西就可以到你上次所做的修改处) 



在当前的单词周围加上"和" 
map *" i"" 


:r file            读入文件file内容，并插在当前行后
:nr file        读入文件file内容，并插在第n行后



# 开启语法高亮
syntax on
# 开启代码智能缩进。例如在写C++程序时，“{”的下一行会自动增加缩进
set cindent
#设置配色方案
colorscheme desert/ron
#设置屏幕字体
set guifont=
#设置编码格式
set enc=utf-8

,                        以相反的方向重复前面的f、F、t或T查找命令
;                        重复前面的f、F、t或T查找命令


：n1,n2 w!command：将文件中n1行至n2行的内容作为command的输入并执行之，若不指
定n1，n2，则表示将整个文件内容作为command的输入
：r!command：将命令command的输出结果放到当前行 

zfap 將游標所在處的那個段落折疊成一行。

zf7G 自游標所在處至全文第 7 行折疊起來。 

5zF 將游標所在處起算 5 行的內容折疊起來。

zi 這是個切換，是折疊與不折疊指令間的切換。

:{range}fo[ld] 跟 zf 一样， Ex 命令而已。

:{range}foldo[pen][!] 同 zo ， Ex 命令。

:{range}foldc[lose][!] 同 zc ， Ex 命令。

zd 删除游标上的 fold 。
zD 删除所有折叠

zo 打开游标上的 fold 。
zO 递回地打开游标上底下所有的 fold 。

zc 把游标上的 fold 折起来。
zC 递回地折起游标上底下所有的 fold 。

zr 將全文的所有折疊依層次通通打開。reduce。 
zR 把整个档案所有的 fold 都打开。

zm 將全文已打開的折疊依層次通通再折疊起來。more。 
zM 把整个档案所有的 fold 都折起来。

zn 打開全文的所有折疊。fold none。
zN 這是 zn 的相對指令，回復所有的折疊。 

zj 把游标移到下一个 fold 上。
zk 把游标移到上一个 fold 上。

批量第一行插入#符号
ctrl+v(有时候可能是ctrl+q)  j移动到块结束
输入I # 按下esc
批量删除插入的#符号
ctrl+v or ctrl+q
选择所有的#
按下d

自动补全。 ctrl+p
gg快速到文章开头

map <M-1> 1gt
map <M-2> 2gt 
map <M-3> 3gt 
map <M-4> 4gt 
map <M-5> 5gt 
map <M-6> 6gt 
map <M-7> 7gt 
map <M-8> 8gt 
map <M-9> 9gt 
map <M-t> :tabnew<CR> 
map <M-w> :tabclose<CR>
map! <M-1> <esc>1gt 
map! <M-2> <esc>2gt 
map! <M-3> <esc>3gt 
map! <M-4> <esc>4gt 
map! <M-5> <esc>5gt 
map! <M-6> <esc>6gt 
map! <M-7> <esc>7gt 
map! <M-8> <esc>8gt 
map! <M-9> <esc>9gt 
map! <M-t> <esc>:tabnew<CR> 
map! <M-w> <esc>:tabclose<CR>

" Use CTRL-S for saving, also in Insert mode
noremap <C-S> :update<CR>
vnoremap <C-S> <C-C>:update<CR>
inoremap <C-S> <C-O>:update<CR> 


[[ start of function
]] end of function


To enter a macro, type:

q<letter><commands>q
To execute the macro <number> times (once by default), type:

<number>@<letter>
So, the complete process looks like:

qd  start recording to register d
... your complex series of commands
q   stop recording
@d  execute your macro
@@  execute your macro again


`. last chagne's exact point


:%s//new value/



vim: Control+W H/J/K/L

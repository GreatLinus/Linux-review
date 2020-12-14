# cat
cat（英文全拼：concatenate）命令用于连接文件并打印到标准输出设备上。
语法
```
cat [-AbeEnstTuv] [--help] [--version] fileName
```
参数说明：
-n 或 --number：由 1 开始对所有输出的行数编号。
-b 或 --number-nonblank：和 -n 相似，只不过对于空白行不编号。
-s 或 --squeeze-blank：当遇到有连续两行以上的空白行，就代换为一行的空白行。
-v 或 --show-nonprinting：使用 ^ 和 M- 符号，除了 LFD 和 TAB 之外。
-E 或 --show-ends : 在每行结束处显示 $。
-T 或 --show-tabs: 将 TAB 字符显示为 ^I。
-A, --show-all：等价于 -vET。
-e：等价于"-vE"选项；
-t：等价于"-vT"选项

- 例1：查阅文件a.txt
```
cat a.txt
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211170147248.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzY3NzU4OA==,size_16,color_FFFFFF,t_70)
- 例2：把a.txt的内容加上行号后输出到b.txt
```
cat -n a.txt > b.txt
cat b.txt
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211170350416.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzY3NzU4OA==,size_16,color_FFFFFF,t_70)
# ls
Linux ls（英文全拼：list files）命令用于显示指定工作目录下之内容（列出目前工作目录所含之文件及子目录)。
语法

```
ls [-alrtAFR] [name...]
```
参数 :

-a 显示所有文件及目录 (. 开头的隐藏文件也会列出)
-l 除文件名称外，亦将文件型态、权限、拥有者、文件大小等资讯详细列出
-r 将文件以相反次序显示(原定依英文字母次序)
-t 将文件依建立时间之先后次序列出
-A 同 -a ，但不列出 "." (目前目录) 及 ".." (父目录)
-F 在列出的文件名称后加一符号；例如可执行档则加 "*", 目录则加 "/"
-R 若目录下有文件，则以下之文件亦皆依序列出

- 例1：列出指定目录的所有目录文件
列出/usr目录

```
ls /usr
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020121117075140.png)
- 例2：列出文件各种信息

```
ls /usr -l
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211170849772.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzY3NzU4OA==,size_16,color_FFFFFF,t_70)
- 例3：列出*带头的文件

```
ls a*
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211171310120.png)
# chomd
Linux chmod（英文全拼：change mode）命令是控制用户对文件的权限的命令
Linux/Unix 的文件调用权限分为三级 : 文件所有者（Owner）、用户组（Group）、其它用户（Other Users）。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211171424640.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzY3NzU4OA==,size_16,color_FFFFFF,t_70)

只有文件所有者和超级用户可以修改文件或目录的权限。可以使用绝对模式（八进制数字模式），符号模式指定文件的权限。

语法

```
chmod [-cfvR] [--help] [--version] mode file...
```
u 表示该文件的拥有者，g 表示与该文件的拥有者属于同一个群体(group)者，o 表示其他以外的人，a 表示这三者皆是。

+表示增加权限、- 表示取消权限、= 表示唯一设定权限。

r 表示可读取，w 表示可写入，x 表示可执行，X 表示只有当该文件是个子目录或者该文件已经被设定过为可执行。
其他参数说明：

-c : 若该文件权限确实已经更改，才显示其更改动作
-f : 若该文件权限无法被更改也不要显示错误讯息
-v : 显示权限变更的详细资料
-R : 对目前目录下的所有文件与子目录进行相同的权限变更(即以递归的方式逐个变更)
--help : 显示辅助说明
--version : 显示版本

用数字来表示权限 r=4,w=2,x=1;3就表示 -wx

- 例1：将a.txt设为所有人可读取

```
chmod ugo+r a.txt
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211171752307.png)
- 例2：将a.txt权限设为所有人都可读写执行

```
chmod  777 a.txt  
ls a* -l
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211172203289.png)
# ps
Linux ps （英文全拼：process status）命令用于显示当前进程的状态，类似于 windows 的任务管理器。
- 例1：显示进程信息

```
ps -A
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211172438870.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzY3NzU4OA==,size_16,color_FFFFFF,t_70)
# kill
Linux kill 命令用于删除执行中的程序或工作
例：删除进程

```
kill 12345
```

# ln
Linux ln（英文全拼：link files）命令是一个非常重要命令，它的功能是为某一个文件在另外一个位置建立一个同步的链接。
当我们需要在不同的目录，用到相同的文件时，我们不需要在每一个需要的目录下都放一个必须相同的文件，我们只要在某个固定的目录，放上该文件，然后在 其它的目录下用ln命令链接（link）它就可以，不必重复的占用磁盘空间。
类似于快捷方式。

例1： 给a.txt创建名为c的链接

```
ln -s a.txt c
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201213160353866.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzY3NzU4OA==,size_16,color_FFFFFF,t_70)
# cp
Linux cp（英文全拼：copy file）命令主要用于复制文件或目录。
语法：

```
cp [options] source dest
```
参数说明：

-a：此选项通常在复制目录时使用，它保留链接、文件属性，并复制目录下的所有内容。其作用等于dpR参数组合。
-d：复制时保留链接。这里所说的链接相当于Windows系统中的快捷方式。
-f：覆盖已经存在的目标文件而不给出提示。
-i：与-f选项相反，在覆盖目标文件之前给出提示，要求用户确认是否覆盖，回答"y"时目标文件将被覆盖。
-p：除复制文件的内容外，还把修改时间和访问权限也复制到新文件中。
-r：若给出的源文件是一个目录文件，此时将复制该目录下所有的子目录和文件。
-l：不复制文件，只是生成链接文件。

- 例1：将a.txt 复制到test文件夹中

```
cp a.txt test
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201213160751928.png)
# mv
Linux mv（英文全拼：move file）命令用来为文件或目录改名、或将文件或目录移入其它位置。

- 例1：将a.txt改名为d.txt

```
mv a.txt d.txt
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201213161105549.png)
- 例2：将test转移到test2中

```
mv test/ test2
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201213161503617.png)
gvb hikmhjnm



# mkdir
Linux mkdir（英文全拼：make directory）命令用于创建目录。

- 例1：创建新目录test2

```
mkdir test2
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201213161312153.png)


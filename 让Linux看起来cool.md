# 让Linux看起来cool

### 命令：cmatrix

你可能看多好莱坞的电影‘黑客帝国’并陶醉于被赋予Neo的能看到在矩阵中任何事物的能力，或者你会想到一幅类似于‘Hacker’的桌面的生动画面。

安装 cmatrix

```
apt-get install cmatrix 
yum install cmatrix
```

### 命令：fortune

试试你未知的运气，终端里有时也有好玩的。

安装 fortune

```
apt-get install fortune (for aptitude based system) 
yum install fortune (for yum based system) 
```

### 命令：Cowsay

一个在终端用ASCII码组成的小牛，这个小牛会说出你想要它说的话。

安装Cowsay

```
apt-get install cowsay (for Debian based OS) 
yum install cowsay (for Red Hat based OS)
```

输出

```
cowsay I Love nix ____________ < I Love nix > ------------ \ ^__^ \ (oo)\_______ (__)\ )\/\ ||----w | || ||
```

如果用管道将‘fortune command’命令重定向到cowsay会怎样呢？

```
fortune | cowsay
```

_________________________________________ / Q: How many Oregonians does it take to \ | screw in a light bulb? A: Three. One to | | screw in the light bulb and two to fend | | off all those | | | | Californians trying to share the | \ experience. / ----------------------------------------- \ ^__^ \ (oo)\_______ (__)\ )\/\ ||----w | || ||

提示：‘|’是管道命令符。通常它是将一个命令的输出作为下一个命令的输入。在上面的例子中‘fortune’的输出作为‘cowsay’命令的输出。管道命令会经常用在脚本和程序编写中。


### 命令：sl (蒸汽机车)

你可能了解 ‘ls’ 命令，并经常使用它来查看文件夹的内容。但是，有些时候你可能会拼写成 ‘sl’ ,这时我们应该如何获得一些乐趣而不是看见“command not found”呢？

安装 sl

```
apt-get install sl
yum -y install sl 
```

### 命令：telnet

非也!非也!!这可不像它平常那样复杂。你可能很熟悉telnet。Telnet 是一个文本化的双向网络协议。这里不需要安装什么东西。你需要的就是一个Linux系统和一个连通的网络。

```
telnet towel.blinkenlights.nl
```

### ASCIIquarium

想要在终端弄一个水族馆该，怎么办？

```
apt-get install libcurses-perl 
cd /tmp 
wget http://search.cpan.org/CPAN/authors/id/K/KB/KBAUCOM/Term-Animation-2.4.tar.gz 
tar -zxvf Term-Animation-2.4.tar.gz 
cd Term-Animation-2.4/ r
perl Makefile.PL && make && make test 
make install
```

下载并安装ASCIIquarium。

```
cd /tmp
wget http://www.robobunny.com/projects/asciiquarium/asciiquarium.tar.gz 
tar -zxvf asciiquarium.tar.gz
cd asciiquarium_1.1/ 
cp asciiquarium /usr/local/bin 
chmod 0755 /usr/local/bin/asciiquarium
```

最后在终端运行“asciiquarium”或者“/usr/local/bin/asciiquarium”，记得不要加引号，神奇的一幕将在你眼前展现。

```
asciiquarium
```


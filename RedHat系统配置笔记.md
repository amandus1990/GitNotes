
### AWS系统帐号
caiusasiniuspullus@gmail.com
系统型号：
Red Hat Enterprise Linux 7.1 (HVM), SSD Volume Type - ami-12663b7a

### 设置帐号
	sudo su
	sudo passwd
加载用户amandus

	cat /etc/group
	sudo useradd -G adm,wheel,systemd-journal amandus
	sudo passwd amandus

### 升级软件
	sudo yum update
yum安装基本软件

	sudo yum install emacs
	sudo yum install gcc
	sudo yum install java
	sudo yum install wget

### 安装Leiningen
	wget https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein
	sudo mv ~/lein /bin
	chmod /bin/lein
	lein
	lein repl

###配置mail系统
	sudo yum install sendmail
	sudo yum install mutt
将/etc/Muttrc文件中的"set from="""改成想要的地址防止自己暴露，记得去掉前面的注释符号。还应该编辑自己的配置文件.muttrc加上"set from="JohnDoe@hello.org""：

	sudo vi /etc/Muttrc
	vi .muttrc
可以测试一下

	echo "hello world2" | mutt -s "test mail" -- caiusasiniuspullus@gmail.com


配置：
	1、安装git，使用命令: $sudo apt-get install git
	2、在github.com创建GitHub账号
	3、生成ssh key, 在本机上使用命令: $ssh-keygen -t rsa -C "your_email@youremail.com",your email是自己的邮箱
	4、回到github.com网站， 进入Account Settings, 选择SSH Keys， Add SSH Key， title可以随便填，但是最好是填写链接电脑的名称或者是可以让你识别出来是哪一台电脑的表示，以便于以后操作， 粘贴key。key就是本机中，~/.ssh/id_rsa.pub中的内容。
	5、测试ssh key是否成功， 使用命令 $ssh -T git@github.com , 如果出现You’ve successfully authenticated, but GitHub does not provide shell access 。这就表示已成功连上github。
	6、配置git的配置文件，username和email(如果已经配置就不用配置了，查看是否配置的方法是：分别查看~/.git/config和/etc/.gitconfig文件，如果其中有关于user.name和user.email的配置就证明已经配置了)

上传：
	1、进入所要上传文件的目录，输入命令：$git init ，如果是git clone下来的项目不需要这一步，只有自己在本地创建的项目才需要初始化
	2、创建一个本地仓库源， 使用命令: $git remote add origin git@github.com:yourname/yourRepo.git , yourname是github的用户名, yourRepo是你要上传到github的仓库，这个需要你在github上添加仓库
	3、比如你要添加一个文件 XXX 到仓库， 使用命令 $git add XXX， 也可以使用:
 $git add . ，自动判读添加哪些文件，然后把这个添加提交到本地仓库，使用命令 $git commit -m "说明这次的提交", 最好把本地仓库源提交到远程github仓库， 使用命令: $git push origin master 


从GitHub克隆项目到本地
	1、到Github的某个仓库， 复制右边"HTTPS clone url
	2、回到要存放的目录， 使用命令示例: $git clone https://github.com/chenyunkang/notebook.git	
	3、如果本地的版本不是最新的，可以使用命令: $git fetch origin, origin是本地仓库
	4、把更新的内容合并到本地分支，可以使用命令: $git merge origin/master, 如果你不想手动合并， 那么使用: $git pull <本地仓库> master //这个命令可以拉去最新版本并自动合并

分支：
还有很多内容，参见网站：https://www.cnblogs.com/duwanjiang/p/5921167.html

# Git ,GitHub入门

> 1：*Git 及GitHub入门*


> 1：*Git 及GitHub入门*

###  1:什么是Git? 什么是GitHub?

- Git
Git 是一个开源的分布式版本控制系统，可以有效并高速地处理从很小到非常大的项目版本管理。
说到Git，首先要明白什么是版本控制及分布式管理系统。

1. 版本控制
版本控制是指在多人协作的软件开发过程当中，对各种代码，配置文件及说明文档变更的管理。最主要的功能就是追踪文件的变更。它会将什么时候，什么人更改了文件的什么内容等信息忠实地记录下来。例如：<br>
![image.png](https://upload-images.jianshu.io/upload_images/16743411-3d3a68839085b23e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2. 分布式管理
提到分布式管理，不得不说Git的诞生。<br>
Linux Torvalds 创建了开源的Linux，并由全世界热心的开源志愿者为Linux系统编写代码。但是随着为其编写代码的人越来越多，队伍越来越壮大，Linux Torvalds仅仅通过自己整合代码已经变得不再现实了，通过版本控制系统来解决代码的管理是最好的方案。但是Linux本人对当时免费并盛行的CVS及SVN等版本控制系统极其厌恶。原因在于 CVS 或 SVN 这些版本控制系统是 **集中式**管理的系统，并且每次提交代码都需要联网。所以Linux选择了一个商业的付费的版本控制系统BitIKeeper，BitKeeper授权给Linux社区可以免费使用这个版本控制系统。但是，Linux社区本身就牛人聚集，BitKipper公司发现，Linux社区里有人试图破解BitKeeper的协议，于是乎，BitKeeper与Linux开源社区合作关系终止。再后来，Linux自己花了两周的时间使用C语言写了一个分布式的版本控制系统，就是Git。现在Git已经成为了最流行的分布式版本控制系统，在2008年GitHub上线，无数的开源项目开始迁移至GitHub。谈完Git的诞生，我们再回到主题，说一说分布式vs集中式。
- 集中式版本控制系统代表：SVN
![image.png](https://upload-images.jianshu.io/upload_images/16743411-fdabf7862ccc93d1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)<br>
集中式版本控制系统以SVN为代表。版本库集中存放在中央服务器。多人协作的项目中，每一台电脑都要先从中央服务器取得最新的版本，再添加或修改好代码以后，  再将自己的代码推送给中央服务器。一旦中央服务器出现了故障，或者崩溃，虽然程序员个人的电脑上有从中央服务器上拉下来的代码，但是中央服务器上有着项目所有的历史版本，想要修复以往的历史版本是非常困难的。

- 分布式版本控制系统代表：Git
![image.png](https://upload-images.jianshu.io/upload_images/16743411-301e63362e25b9f0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)<br>
分布式版本控制系统则没有中央服务器这样的概念，每个人的电脑都是一个完整的版本库，当然，分布式版本控制系统通常也存在一台充当中央服务器的电脑，方便程序员更新以及推送最新版本。即使这个所谓的"中央服务器" 挂掉，每个人的电脑上都保留着历史版本的信息。这样来看，分布式版本控制比集中式版本控制的安全性要高。当然Git相比于SVN的优势远远不止这些，详见：[Git与SVN区别](http://www.runoob.com/git/git-tutorial.html)。

- GitHub
GitHub是一个开源的私有软件项目的托管平台，于2008年上线。GitHub只支持git作为唯一的版本库格式进行托管。
### 2：GitHub的配置工作
1. 首先，注册GitHub账号，注册完毕后点击头像位置的settings。
2. 在左侧栏的Profile中 找到"SSH and GPG keys"，然后你会看到"New SSH key".这个按钮，先不要着急去点击它，你会看到下面有一个可点击的链接"Check out our guide to generating SSH keys or troubleshoot common SSH Problems."，点击 [generating SSH keys](https://help.github.com/articles/generating-an-ssh-key/)
并且选择第三项： [Generating a new SSH key and adding it to the ssh-agent](https://help.github.com/en/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)。

3. 按照上面的提示操作即可：打开GitBash ，输入命令：`` ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`` ，输入完毕后，敲入三次回车，即可。注意 后面需要填写你自己的邮箱。
4. 运行命令``ls -a ~/.ssh``。当执行完命令`` ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`` 后，会在家目录下生成一个.ssh的目录。运行命令``ls -a ~/.ssh``后，可以看到 在.ssh目录下有两个文件 “id_rsa”以及"id_rsa.pub"。这两个东西就公钥和私钥，是你本地的Git仓库与GitHub 之间的钥匙和锁。其中"id_rsa"就是钥匙，而"id_rsa.pub"即是锁。
5.  接下来点击 刚刚说过的 "New SSH key" 按钮，Title就是你这个SSH key的名字，下面的key的内容需要将你的公钥的内容全部复制进去，在GitBash上执行命令``cat ~/.ssh/id_rsa.pub``. 然后将"ssh-rsa"至"your_email@example.com" 的全部内容复制并粘贴到key里面。添加完毕后点击 “Add SSH key” 按钮。
6. 在GitBash上输入命令``ssh -T git@github.com`` .如果看到返回这样的信息：``Hi DobbyKimmy! You've successfully authenticated, but GitHub does not provide shell access.`` ,那么说明配置成功。如果失败，则在GitHub上运行``rm -rf ~/.ssh``后从第一步重新开始。如果在以后，购买了新的主机，那么就在新的PC上重新生成一个SSH key 即可，它可以和之前的key共存。
###  3:Git的配置工作
````
git config --global user.name 你的英文名                                                   
git config --global user.email 你的邮箱                                                     
git config --global push.default matching
git config --global core.quotepath false
git config --global core.editor "vim"
````
这五句话一定要执行，配置好Git以后，才可以保证以后不会报错。

###  4:Git的本地使用
1. ``git init``
选择一个空目录,GitBash Here,然后执行命令``git init``。该命令的作用是初始化，执行完该命令后，在当前目录下会创建一个名叫.git的目录。
2. ``git status -sb``
接下来在当前目录再创建两个个文件如：index.html,即输入命令：
````
touch index.html
mkdir css
cd css
touch style.css
cd ../
````
执行命令``git status -sb``后，会返回这样的结果：
````
?? css/
?? index.html
````
命令``git status `` 是用来查看当前git的状态的，-s代表显示总结即：summary ; -b 表示显示分支即：branch。再创建文件以后，git 不知道该如何处理这两个文件，所以会出现"??"这样的符号。
3. ``git add``
命令``git add`` 可以将创建的文件添加到暂存区，可以使用：``git add index.html`` 然后再使用 ``git add css/style.css`` 一次一次地将文件添加进暂存区，也可以 一次性地 ``git add . `` 此命令表示一次性将当前目录里所有的变动都添加到暂存区。再执行完添加暂存区的命令以后 再次使用 ``git status -sb`` 可以发现 原来红色的"??"变成了绿色的"AA"。A的意思就是add,也是是说，你告诉git，这些变动的文件我要加入到仓库中。
4. ``git commit  -m"xxx"``
``git commit  -m"xxx"`` 命令可以将add过的内容，即：在git暂存区的内容正式提交到本地仓库（.git就是本地仓库）-m的含义是message 即：为你这次提交说明信息，且-m这个参数是必须有的。除了-m参数外，还有一个参数 -a.如：使用命令``git commit -am "xxx"`` 该命令会将本地工作区修改过还未放入git暂存区的文件一并提交上去，相当于 ``git add .``命令 与 ``git commit -m"xxx"`` 两个命令一并使用,并且这个命令可以确保所有的变动提交到本地仓库。在运行完``git commit -am "添加了一些变动"``命令后，使用命令``git status -sb``后，发现文件没有变动了，这是因为文件变动已经记录在仓库里了 这时可以使用命令：``git log `` 查看历史变动，历史变动信息如下：
````
Author: DobbyKim <1175088275@qq.com>
Date:   Thu Apr 4 15:36:37 2019 +0800

    添加了一些文件
````
5. ``git log``
上文已经使用过``git log `` 命令了，``git log``是一个非常重要的命令，可以查看项目所有的历史变动信息，而且可以看到更新人的姓名 以及邮箱账号。
6. 文件变动
在提交至本地仓库以后，我们对index.html进行编辑写入一些内容后保存，这是我们再去看``git status -b``,可以看到 git的状态变成了：
````
 M index.html
````
M的颜色是红色，其含义为Modified，表示index.html文件被修改了，如果你想让改动保存到仓库中，需要``git add . `` 将改动保存到暂存区，然后再commit 执行命令``git commit -am "编辑了index.html"``。执行完add 和 commit操作后，使用命令``git status -sb`` 发现文件没有变动了，使用``git log ``:
````
$ git log
commit c96f1b9c58c517501d1d7544ef5ff76f01078d25 (HEAD -> master)
Author: DobbyKim <1175088275@qq.com>
Date:   Thu Apr 4 16:04:48 2019 +0800

    编辑了index.html

commit 138a29bcdd7b2b2a19e7d5a7f8150da5666623f9
Author: DobbyKim <1175088275@qq.com>
Date:   Thu Apr 4 15:36:37 2019 +0800

    添加了一些文件

````
###  5:Git 本地仓库上传到GitHub
1. 首先在GitHub上新建一个空仓库:<br>
![image.png](https://upload-images.jianshu.io/upload_images/16743411-f71b095833675a91.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
<br>
只需要设置仓库的名字，其他的一概不填，因为如果填写了就不是空仓库了。
2. 按照GitHub 上的指示进行操作
首先要选择SSH路径。建立好空仓库以后GitHub会在下面出现命令提示。
create a new repository on the command line
````
echo "# demo" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:DobbyKimmy/demo.git
git push -u origin master
````
push an existing repository from the command line
````
git remote add origin git@github.com:DobbyKimmy/demo.git
git push -u origin master
````
本地仓库上传至GitHub只需要执行git remote和 git push 两个命令。origin 是 ``git@github.com:DobbyKimmy/demo.git``这个仓库的代号，remote命令的作用是让本地仓库与GitHub远程仓库建立联系。git push 则是将本地仓库内容推送到远程仓库上，origin还是远程仓库的代号，master代表默认的主分支。
###  6:下载GitHub上的仓库至本地
示例：创建一个GitHub仓库，这一次需要建立一个非空仓库。<br>
![image.png](https://upload-images.jianshu.io/upload_images/16743411-0d20e66a1b302f70.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
<br>
respository name还是仓库的名字，description 为仓库的说明信息，勾选Initialize this repository with a README 是用于在创建仓库时初始化README.md文件。其中.gitignore文件的作用是忽略Git中不想提交的文件，在.gitignore文件中可以进行一些配置，来避免某些文件的提交，比如：写上``/node_modules/ ``，``/.vscode/``就可以避免node_modules/和 .vscode/目录上传到GitHub上了。 License是开源许可证书，这里面我选择了MIT的开源许可证。创建好仓库以后，复制链接：<br>
![](https://upload-images.jianshu.io/upload_images/16743411-b075812171a440fa.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)<br>
进入到你想clone的目录下，在GitBash上输入：``git clone "复制的SSH URL"``就可以下载仓库了。
###  7:上传更新
下载到本地仓库以后，上传更新很简单，只需要先后执行：
1. git add.
2. git commit -am "xxx"
3. **git pull**
其中 ``git pull``命令的作用是让本地同步好远程仓库的代码。如果一个项目，你做出了修改，你的程序员同事也做出了修改，并且先于你一步提交了代码，那么你本地仓库的代码就不是最新版本的了。这时候上传代码到远程仓库会出现错误，只需要先将最新的代码从远程仓库pull 下来再次上传即可。
4. git push 

###  8:git pull 和 git clone的区别
在运用这两个命令时，从应用场景来看，git clone 是本地没有仓库时，将远程的仓库下载下来，git pull 命令则是将远程仓库新commit的数据拉到本地，再与本地仓库进行merge。git clone和 git pull 都是下载代码。从远程服务器克隆一个一模一样的**版本库**到本地，复制的是整个版本库，叫做clone,这是一个从无到有的过程。git pull 是拉去远程分支更新到本地仓库的操作，git pull 相当于，从远程仓库获取最新版本，然后再与本地分支merge的过程，这是一个从有到全面，从非同步到同步的过程。
:# Git-
Git的基本使用规则:
    1、首先安装Git，可以从官网 https://git-scm.com/downloads 下载，也可以从雷锋提供的镜像下载 https://pan.baidu.com/s/1kU5OCOB#list/path=%2Fpub%2Fgit。 如版本号Git-2.7.1.2-64-bit，建议一路next的时候，仔细看一哈每个选项。最后桌面出现【Git Bash】图标。
    2、Git有三个区域【工作区】、【暂存区】、【版本库】
    	【工作区】即本地可看得见的区域。新建一个文件夹，使用Git命令【git init】后即成为一个本地工作区。
        【暂存区】即本地执行Git命令【Git add 】之后就将本地文件添加到了暂存区。
	【版本库】即本地或者远程的仓库，使用Git【git commit 】后就将文件提交到了仓库中。
    3、安装好Git Bash后，执行命令【it config --global user.name "xxx"】和【git config --global user.email "xxx@xx.com"】，这样每次提交后将使用配置的个人用户名称和电子邮件地址作为提交信息。
    4、创建本地仓库
       【mkdir MyGit】->【git init】->【touch localFile.txt】->【git add localFile】->【git commit -m "dedu local repository test"】
    5、创建远程仓库（GitHub）
       ①使用Https协议：使用GitHub账号创建一个Repository，点击Clone or download复制URL链接。
       	创建一个文件夹，使用【git clone URL】复制远程的仓库，然后会在这个文件夹中Down下仓库中的文件，即是一个本地仓库。在本地仓库中操作并提交后就可以使用Git命令【git push】推送本地仓库文件到远程仓库，这是输入账号密码验证就一可以成功提交了。
       ②使用SSH加密：使用Https协议提交时每次都需要密码验证且上传速度慢，此时可以使用SSH加密。
        使用Git命令【ssh-keygen -t rsa -C "youremail@example.com"】生成SSH Key，在/c/Users/xxx/.ssh目录下有生成的.pub结尾的文件，用notepad打开并复制。在GitHub的Setting中，SSH and GPG keys中，New SSH keys，然后把复制内容添加到key文本框中再点击Add SSH key即可。【ssh -T git@github.com】可以来测试是否连通。
	然后同步骤4一样使用【git clone】，最后Push后就不用再输入账号密码验证；或者使用【git remote add origin git@github.com:dedu18/Git-.git】，然后把本地库的所有内容推送到远程库上【git push -u origin master】；
	
   6、其他常用命令
      【git remote remove origin】 取消关联的仓库
      【git status 】 查看此仓库状态
      【git diff 】 查看文件和仓库中的差异
      【git log 】 查看日志
      【git reset --hard HEAD^   git reset --hard 3628164 】回退到某版本
      【git reflog 】查看命令历史
      【git rm 】删除已提交的文件
      【git checkout -- 文件 】 把文件在工作区的修改全部撤销，分两种情况（自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；文件已经添加到暂存区后，又作了修改，现在撤销修改就回到添加到暂存区后的状态。）

# 版本控制工具帮助文档

```
切换分支
git checkout dev
git checkout master

git add .
git commit -m ""
git config user.name "username"
git config user.email "email@email.com"
git config --global user.name


分支
git branch testing 创建新分支 

git log 查看各个分支当前所指的对象
git log --oneline --decorate --graph --all 查看所有分支的情况

git checkout testing 切换分支
git checkout -b iss53 创建iss53分支并且切换到iss53分支 -b表示git checkout iss53
是一下两条命令的缩写
git branch iss53
git checkout iss53

git branch -d hotfix 删除分支

git merge hotfix 合并分支当当前分支下面
```



Git介绍

> <https://git-scm.com/docs/git>

Git工具使用帮助文档

> 参考文档
>
> 中文：https://help.github.com/cn
>
> English：https://help.github.com/en

注册



### [为计算机上的*每个*仓库设置 Git 用户名](https://help.github.com/cn/github/using-git/setting-your-username-in-git#undefined)

1. 打开 Git Bash。

2. 设置 Git 用户名：

   ```shell
   $ git config --global user.name "Mona Lisa"
   ```

3. 确认您正确设置了 Git 用户名：

   ```shell
   $ git config --global user.name
   > Mona Lisa
   ```

### [为一个仓库设置 Git 用户名](https://help.github.com/cn/github/using-git/setting-your-username-in-git#setting-your-git-username-for-a-single-repository)

1. 打开 Git Bash。

2. 将当前工作目录更改为您想要在其中配置与 Git 提交关联的名称的本地仓库。

3. 设置 Git 用户名：

   ```shell
   $ git config user.name "Mona Lisa"
   ```

4. 确认您正确设置了 Git 用户名：

   ```shell
   $ git config user.name
   > Mona Lisa
   ```

### [在 Git 中设置您的提交电子邮件地址](https://help.github.com/cn/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address#setting-your-commit-email-address-in-git)

您可以使用 `git config` 命令更改与 Git 提交关联的电子邮件地址。 您设置的新电子邮件地址将在从命令行推送到 GitHub 的任何未来提交中显示。 在您更改提交电子邮件地址之前进行的任何提交仍与之前的电子邮件地址关联。

#### [为计算机上的每个仓库设置电子邮件地址](https://help.github.com/cn/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address#setting-your-email-address-for-every-repository-on-your-computer)

1. 打开 Git Bash。

2. Set an email address in Git. You can use your [GitHub-provided `no-reply` email address](https://help.github.com/cn/articles/setting-your-commit-email-address) or any email address.

   ```shell
   $ git config --global user.email "email@example.com"
   ```

3. 确认在 Git 中正确设置了电子邮件地址：

   ```shell
   $ git config --global user.email
   email@example.com
   ```

4. Add the email address to your GitHub account by [setting your commit email address](https://help.github.com/cn/articles/setting-your-commit-email-address), so that your commits are attributed to you and appear in your contributions graph.

#### [为一个仓库设置电子邮件地址](https://help.github.com/cn/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address#setting-your-email-address-for-a-single-repository)

GitHub 使用在您的本地 Git 配置中设置的电子邮件地址将从命令行推送的提交与您的 GitHub 帐户相关联。

您可以更改与您在一个仓库中所进行的提交关联的电子邮件地址。 此操作将覆盖这一个仓库中的全局 Git 配置设置，但不会影响任何其他仓库。

1. 打开 Git Bash。

2. 将当前工作目录更改为您想要在其中配置与 Git 提交关联的电子邮件地址的本地仓库。

3. Set an email address in Git. You can use your [GitHub-provided `no-reply` email address](https://help.github.com/cn/articles/setting-your-commit-email-address) or any email address.

   ```shell
   $ git config user.email "email@example.com"
   ```

4. 确认在 Git 中正确设置了电子邮件地址：

   ```shell
   $ git config user.email
   email@example.com
   ```

5. Add the email address to your GitHub account by [setting your commit email address](https://help.github.com/cn/articles/setting-your-commit-email-address), so that your commits are attributed to you and appear in your contributions graph.

# 创建仓库

要将项目放在 GitHub 上，您需要创建一个仓库来存放它。

```html
https://help.github.com/cn/github/getting-started-with-github/create-a-repo
```



### [提交您的第一个更改](https://help.github.com/cn/github/getting-started-with-github/create-a-repo#commit-your-first-change)

A *提交*就像是项目中所有文件在特定时间点的快照。

创建新仓库时，您使用*自述文件*对其进行了初始化。 *自述文件*是详细介绍项目的好工具，您也可以添加一些文档，例如介绍如何安装或使用项目的文档。 *自述文件*的内容自动显示在仓库的首页上。

让我们提交对*自述文件*的更改。

1. 在仓库的文件列表中，单击 **README.md**。

# 复刻仓库

*复刻*是仓库的副本。 通过复刻仓库，您可以自由地尝试更改而不会影响原始项目。



### [让复刻保持同步](https://help.github.com/cn/github/getting-started-with-github/fork-a-repo#keep-your-fork-synced)

您可能为了对*上游*或原始仓库提议更改而复刻项目。 在这种情况下，最好定期将您的复刻与上游仓库同步。 为此，您需要在命令行上使用 Git。 您可以使用刚才复刻的 [octocat/Spoon-Knife](https://github.com/octocat/Spoon-Knife) 仓库练习设置上游仓库！



#### [第 1 步：设置 Git](https://help.github.com/cn/github/getting-started-with-github/fork-a-repo#step-1-set-up-git)

如果尚未[设置 Git](https://help.github.com/cn/articles/set-up-git)，您应该先设置它。 不要忘记[从 Git 设置向 GitHub 验证](https://help.github.com/cn/articles/set-up-git#next-steps-authenticating-with-github-from-git)。

#### [第 2 步：创建复刻的本地克隆](https://help.github.com/cn/github/getting-started-with-github/fork-a-repo#step-2-create-a-local-clone-of-your-fork)

现在，您有了 Spoon-Knife 仓库的复刻，但您的计算机上还没有该仓库中的文件。 让我们在计算机上本地创建复刻的*克隆*。

1. 在 GitHub 上，导航到 Spoon-Knife 仓库的**复刻**。
2. Under the repository name, click **Clone or download**.

To clone the repository using HTTPS, under "Clone with HTTPS", click . To clone the repository using an SSH key, including a certificate issued by your organization's SSH certificate authority, click **Use SSH**, then click .



#### [第 3 步：配置 Git 以将您的复刻与原始 Spoon-Knife 仓库同步](https://help.github.com/cn/github/getting-started-with-github/fork-a-repo#step-3-configure-git-to-sync-your-fork-with-the-original-spoon-knife-repository)

为了对原始仓库提议更改而复刻项目时，您可以配置 Git 以将更改从原始或*上游*仓库拉取到复刻的本地克隆。

1. 在 GitHub 上，导航到 [octocat/Spoon-Knife](https://github.com/octocat/Spoon-Knife) 仓库。
2. Under the repository name, click **Clone or download**.









































































2.1Git基础-获取git仓库

git是一个内容寻址的文件系统

两种方法

```
1.是在现有项目和目录下导入所有文件到Git中
	git init
	该命令将创建一个名为.git的子目录，这个子目录含有你初始化的Git仓库中所有的必须文件，这些文件是Git是仓库的骨干。但是在这个时候，我们仅仅是做了一个初始化的操作，你的项目里的文件还没有被跟踪。
2.从一个服务器克隆一个现有的Git仓库
	git clone [url] [自定义仓库名字]
	git clone https://github.com/libgit2/libgit2
	获得已经存在的Git仓库拷贝，拷贝该仓库的几乎所有的数据，默认配置下远程Git仓库中每一个文件的每一个版本都被拉去下来
```

状态简述

```
git status命令的输出状态的报告
git status -s 
git status --short
新添加未跟踪的前面有??标记，新添加到
```


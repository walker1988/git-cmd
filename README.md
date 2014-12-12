git命令的基本用法
===============
>工作区：本地库目录

>版本库：本地库目录中的.git目录

>暂存区

>master分支

>HEAD：指向master分支的指针

###1、配置全局用户名和邮箱
<pre>
$ git config --global user.name "walker"
$ git config --global user.email "walker@163.com"
</pre>

###2、从远程库克隆项目(*git clone*)
<pre>
$ git clone git@github.com:walker1988/test.git
Cloning into 'test'...
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (3/3), done.
Checking connectivity... done.
</pre>

###3、查看本地工作区的状态(*git status*)
<pre>
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
</pre>

###4、将文件修改添加到暂存区(*git add filename*)
<pre>
$ git add README.md 
</pre>

###5、再次查看本地工作区的状态(*git status*)
<pre>
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   README.md
</pre>

###6、将暂存区的文件修改提交到master分支(*git commit -m "remark"*)
<pre>
$ git commit -m "修改READ.md文件"
[master 3f57873] 修改READ.md文件
 1 file changed, 33 insertions(+), 4 deletions(-)
 rewrite README.md (78%)
</pre>

###7、查看版本库中最新版本与工作区指定文件的区别(*git diff HEAD -- fileName*)
<pre>
$ git diff HEAD -- README.md 
diff --git a/README.md b/README.md
index 166a302..73f349e 100644
--- a/README.md
+++ b/README.md
@@ -83,3 +83,4 @@ To git@github.com:walker1988/test.git
    15dffab..3f57873  master -> master
 
+have a try
</pre>

###8、撤销未提交到暂存区的修改，即个性文件后没有执行git add操作(*git checkout -- filename*)
<pre>
$ echo "goodbye today." > newfish.log 
$ cat newfish.log 
goodbye today.
$ git checkout -- newfish.log 
$ cat newfish.log 
$ 
</pre>

###9、撤销已提交到暂存区但未提交到主分支的修改，即执行了git add，但尚未执行git commit(*git reset HEAD filename*)
<pre>
$ echo "goodbye today." > newfish.log 
$ cat newfish.log 
goodbye today.
$ git add newfish.log 
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   newfish.log

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

$ git reset HEAD newfish.log 
Unstaged changes after reset:
M	README.md
M	newfish.log
$ cat newfish.log 
goodbye today.
$ git checkout -- newfish.log 
$ cat newfish.log 
</pre>

###10、删除文件(*git rm filename*)
<pre>
$ rm newfish.log 
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	deleted:    newfish.log

no changes added to commit (use "git add" and/or "git commit -a")
$ git rm newfish.log
rm 'newfish.log'
$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	deleted:    newfish.log

</pre>

###11、将master分支的修改推送到远程仓库(*git push*)
<pre>
$ git push
Counting objects: 5, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 772 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To git@github.com:walker1988/test.git
   15dffab..3f57873  master -> master
</pre>

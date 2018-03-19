# [**Git 如何删除远程服务器文件同时保留本地文件**](https://segmentfault.com/a/1190000009525388)

查看端口：netstat -nab

#合并某个分支上的单个commit**

feature 分支上的commit 62ecb3 非常重要，它含有一个bug的修改，或其他人想访问的内容。无论什么原因，你现在只需要将62ecb3 合并到master，而不合并feature上的其他commits，所以我们用git cherry-pick命令来做：


```
git checkout master  
git cherry-pick 62ecb3 
```
#合并某个分支上的一系列commits
>假设你需要合并feature分支的commit76cada ~62ecb3 到master分支
首先需要基于feature创建一个新的分支，并指明新分支的最后一个commit：

`git checkout -bnewbranch 62ecb3 ` 

>rebase这个新分支的commit到master（--ontomaster）。76cada^ 指明你想从哪个特定的commit开始。

`git rebase --ontomaster 76cada^  `

#git删除远程
`git push origin --delete <branchName>`

删除index.lock
>index.lock    rm -f ./msg/.git/index.lock
删除文件夹
rm -f *

## git代理
> git config --global http.proxy
> git config --global --unset http.proxy

## git删除所有记录，全新仓库
> git checkout --orphan latest_branch
> git add -A
> git commit -am "commit message"
> git branch -D master
> git branch -m master
> git push -f origin master
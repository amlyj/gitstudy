```shell
$ git -c core.quotepath=false push --progress --porcelain origin refs/heads/develop:develop

error: failed to push some refs to 'git@git.amlyj.com:IaaS/iaasms.git'
To git@git.amlyj.com:IaaS/iaasms.git
!	refs/heads/develop:refs/heads/develop	[rejected] (fetch first)
hint: Updates were rejected because the remote contains work that you do
Done
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

$ git -c core.quotepath=false fetch origin --progress --prune
remote: Counting objects: 64, done.[K
remote: Compressing objects: 100% (64/64), done.[K
remote: Total 64 (delta 52), reused 0 (delta 0)[K
From git.amlyj.com:IaaS/iaasms
   ca1eca8..9be6884  develop    -> origin/develop

$ git -c core.quotepath=false stash save "Uncommitted changes before Update at 17-9-9 下午1:01"
$ git -c core.quotepath=false merge origin/develop --no-stat -v
$ git -c core.quotepath=false stash pop
$ git -c core.quotepath=false add --ignore-errors -- iaasms/settings.py
$ git -c core.quotepath=false push --progress --porcelain origin refs/heads/develop:develop

Counting objects: 42, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (12/12), done.
Writing objects: 100% (12/12), 1.00 KiB | 0 bytes/s, done.
Total 12 (delta 10), reused 0 (delta 0)
To git@git.amlyj.com:IaaS/iaasms.git
    refs/heads/develop:refs/heads/develop	9be6884..82fe547
Done

```

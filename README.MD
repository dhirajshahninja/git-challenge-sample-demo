## git-challenge-sample-demo

### Steps that follow to simulate the task:-

- Update the `/.git/config` file in a local project with below config.
```
[pull]
          rebase = true
```
- Otherwise you can set that globally by below command.
```
git config --global pull.rebase true
```

##### Note:- Above config will rebase the current branch with a branch from where we pull the latest code.
-----
### Simulation scenario:-
- Create a sample repository.
- Init commit with readme file in master branch.
- Then create two branch with name `add-echo` and `add-reverse` from master.
- Commit the changes in both branch. Now, both branch ahead from master.
- Add the readme file commit in master. And both branch 1 commit ahead and behind from master.
- Now, checkout the branch `add-echo` and take a latest pull from master with below command. As we have already set the config to rebase the branch on pull we do not pass the `--rebase` everytime.
```
git pull origin master
```
- After that, Pushed the changes to `add-echo` so, the `add-echo` will be no more behind from master. And then checkout to the `master` and take a pull from `add-echo`.
- We need to follow the same pattern as above for another branch `add-reverse` branch.
- Check the log using command `git log` and confim the commits.

----
### Simulation Logs:-

```
commit 1226116878b8cd6b525d6d93f1bce36360c4a7ff (HEAD -> master, origin/add-reverse, add-reverse)
Author: dhirajshahninja <dhiraj.shah.ninja@gmail.com>
Date:   Sat Jul 27 14:38:09 2019 +0530

    add-reverse route commit

commit d10181ff297465f0eec6b5898a1c68393389a4f4 (origin/master, origin/add-echo, add-echo)
Author: dhirajshahninja <dhiraj.shah.ninja@gmail.com>
Date:   Sat Jul 27 14:36:16 2019 +0530

    add-echo route commit

commit 46d0f6bdf9ef0b31952394c56410971169e17e42
Author: dhirajshahninja <dhiraj.shah.ninja@gmail.com>
Date:   Sat Jul 27 14:39:05 2019 +0530

    Update readme file in master

commit 4dc407221dfe2ab3b79b963a25fd9eb0e305f435

    add-reverse route commit

commit d10181ff297465f0eec6b5898a1c68393389a4f4 (origin/add-echo, add-echo)
Author: dhirajshahninja <dhiraj.shah.ninja@gmail.com>
Date:   Sat Jul 27 14:36:16 2019 +0530

    add-echo route commit

commit 46d0f6bdf9ef0b31952394c56410971169e17e42
Author: dhirajshahninja <dhiraj.shah.ninja@gmail.com>
Date:   Sat Jul 27 14:39:05 2019 +0530

    Update readme file in master

commit 4dc407221dfe2ab3b79b963a25fd9eb0e305f435
Author: dhirajshahninja <dhiraj.shah.ninja@gmail.com>
Date:   Sat Jul 27 14:34:33 2019 +0530

    Init commit
```
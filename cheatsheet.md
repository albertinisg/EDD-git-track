# Basics

* Initialize the repository

  ``` console
  git init
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git init
  Initialized empty Git repository in /home/yeyeto2788/Downloads/git_exercises/.git/
  ```

* Set details of the repository

  * Linux users

    ```console
    git config --global user.email "you@example.com"                                                                                   
    git config --global user.name "Your Name"
    git config --global lga log --graph --oneline --decorate –all​
    git config --global lg log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative​
    git config --global core.editor vim
    ```

  * Windows users

    ```console
    git config --global user.email "you@example.com"                                                                                   
    git config --global user.name "Your Name"
    git config --global lga log --graph --oneline --decorate –all​
    git config --global lg log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative​
    git config --global core.editor notepad
    ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git config user.email "test@test.com"
  git_user@Desktop:~/Downloads/git_exercises$ git config user.name 'testrobot'  
  ```

  * Generate Keygen (SSH)

    ```console
    ssh-keygen -t rsa
    ```

  ## command(s) output

  ```console
    Generating public/private rsa key pair.
    Enter file in which to save the key (/home/amartin/.ssh/id_rsa): /tmp/.ssh/id_rsa
    Enter passphrase (empty for no passphrase): 
    Enter same passphrase again: 
    Your identification has been saved in /tmp/.ssh/id_rsa.
    Your public key has been saved in /tmp/.ssh/id_rsa.pub.
    The key fingerprint is:
    SHA256:Ystzx+CTXcbZdj5bAlg1I97NLb84/Bc7G4nr493fdps amartin@dellXPS
    The key's randomart image is:
    +---[RSA 3072]----+
    |            . +  |
    |           . + =.|
    |            o o +|
    |           + o o |
    |      o S . * o o|
    |     o + = o.oo+o|
    |      + = +  =.==|
    |       o o   .=+%|
    |            o+.E@|
    +----[SHA256]-----+ 
  ``` 

* Check details of recently created repository

  ```console
  git status
  ```

* Create a file and check status

  ```console
  git status
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ nano 1st_file.txt
  git_user@Desktop:~/Downloads/git_exercises$ git status
  On branch master

  No commits yet

  Untracked files:
    (use "git add <file>..." to include in what will be committed)

          1st_file.txt

  nothing added to commit but untracked files present (use "git add" to track)
  ```

* Add file to repository

  ```console
  git add <filename>
  ```

* Commit added change to the repository

  ```console
  git commit -m <message>
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git commit -m 'Adding first file to repo'                                     
  [master (root-commit) 168d1ca] Adding first file to repo
   1 file changed, 1 insertion(+)
   create mode 100644 1st_file.txt
  ```

* Check again the repository

  ```console
  git status
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git status
  On branch master
  nothing to commit, working tree clean
  ```

* Now see the commit until now using one of the commands below

  ```console
  git log
  git log -n 5
  git log --oneline
  git log --oneline --graph
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git log
  commit 168d1ca57c43f6b96aa4b145b205533db8b06d3f (HEAD -> master)
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 14:28:29 2019 +0200

      Adding first file to repo
  ```

# Staging

* Make other changes into the file added and see the details

  ```console
  git diff
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git diff 1st_file.txt
  diff --git a/1st_file.txt b/1st_file.txt
  index 6f58ba1..6f8a3c5 100644
  --- a/1st_file.txt
  +++ b/1st_file.txt
  @@ -1 +1 @@
  -wujuuuu first file
  +wujuuuu first file and now with more changes
  ```

* Add the changes into the repository and see the stage details

  ```console
  git add <filename>
  git diff --staged <filename>
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ nano 1st_file.txt
  git_user@Desktop:~/Downloads/git_exercises$ git diff
  diff --git a/1st_file.txt b/1st_file.txt
  index 6f8a3c5..51348bb 100644
  --- a/1st_file.txt
  +++ b/1st_file.txt
  @@ -1 +1 @@
  -wujuuuu first file and now with more changes
  +wujuuuu first file and now with more changes that are going to be deleted

  ```

* Make more changes into the file and view details again

  ```console
  git diff <filename>
  ```

**NOTE:** Look at the different outputs.

* Commit changes done.

  ```console
  git commit -m <message>
  ```

# Branching

* Let's see what we got on the repository so far.

  ```console
  git ls-tree <branch> <directory>
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git ls-tree master .
  100644 blob 2b034fcc70807400e030b3de65c3fae243b1658e    1st_file.txt
  ```

* Let's see what branch we are on and the available ones.

  ```console
  git branch
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git branch
  * master
  ```

* Create a new branch and see branches again.

  ```console
  git branch <branch_name>
  git branch
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git branch middle
  git_user@Desktop:~/Downloads/git_exercises$ git branch
  * master
    middle
  ```

* Move into the new branch.

  ```console
  git checkout <branch_name>
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git checkout middle
  Switched to branch 'middle'
  ```

* Is anything on the newly created branch?

  ```console
  git status
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git status
  On branch middle
  nothing to commit, working tree clean
  ```

* Create a file a commit it changes and see what we got so far

  ```console
  git add <filename>
  git commit -m <message>
  git log --oneline --graph --all
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ nano 2nd_file.txt
  git_user@Desktop:~/Downloads/git_exercises$ git add 2nd_file.txt
  git_user@Desktop:~/Downloads/git_exercises$ git commit -m "Adding second file into repo!!"
  git commit -m "Adding second file into repogit add 2nd_file.txt "
  [middle 158f446] Adding second file into repogit add 2nd_file.txt
   1 file changed, 1 insertion(+)
   create mode 100644 2nd_file.txt
  git_user@Desktop:~/Downloads/git_exercises$ git log --oneline --graph
  * 158f446 (HEAD -> middle) Adding second file into repogit add 2nd_file.txt
  * 2eab953 (master) My second commit
  * 168d1ca Adding first file to repo
  ```

* Let's see the changes between branches

  ```console
  git diff <branch_name1> <branch_name2>
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git diff master middle
  diff --git a/2nd_file.txt b/2nd_file.txt
  new file mode 100644
  index 0000000..d064728
  --- /dev/null
  +++ b/2nd_file.txt
  @@ -0,0 +1 @@
  +wujuuu 2nd file
  ```

# Merging

## Fast forward merge

* Let's have everything on first branch (should be master)

  ```console
  git checkout master
  git merge <branch_name>
  ```

  or

  ```console
  git merge <branch_name1> <branch_name2>
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git checkout master
  Switched to branch 'master'
  git_user@Desktop:~/Downloads/git_exercises$ git merge middle
  Updating 2eab953..158f446
  Fast-forward
   2nd_file.txt | 1 +
   1 file changed, 1 insertion(+)
   create mode 100644 2nd_file.txt
  ```

### Another merge

* Create branch from master

  ```console
  git checkout master
  git checkout -b <branch_name>
  ```

  ## command(s) outputs

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git checkout master
  Already on 'master'
  git_user@Desktop:~/Downloads/git_exercises$ git checkout -b final
  Switched to a new branch 'final'
  ```

* Edit both files and commit the changes again

  ```console
  git add <filename1>
  git add <filename2>
  ```

  or

  ```console
  git add *
  ```

  then

  ```console
  git commit -m <message>
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ nano 2nd_file.txt
  git_user@Desktop:~/Downloads/git_exercises$ nano 1st_file.txt
  git_user@Desktop:~/Downloads/git_exercises$ git add *
  git_user@Desktop:~/Downloads/git_exercises$ git commit -m 'Modification of both files'
  [final 0e3628f] Modification of both files
   2 files changed, 3 insertions(+), 1 deletion(-)
  ```

* Go now to master

  ```console
  git checkout master
  ```
  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git checkout master
  Switched to branch 'master'
  ```

* Make changes on one of the files and commit them

  ```console
  git add <filename1>
  git commit -m <message>
  ```
  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ nano 1st_file.txt
  git_user@Desktop:~/Downloads/git_exercises$ git add 1st_file.txt
  git_user@Desktop:~/Downloads/git_exercises$ git commit -m "just a change for conflic purposes"
  [master 4bfcefd] just a change for conflic purposes
   1 file changed, 1 insertion(+), 1 deletion(-)
  ```

* Now try to merges changes from branch 2 (recently created)

  ```console
  git merge <branch_name3>
  ```
  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git merge final
  Auto-merging 1st_file.txt
  CONFLICT (content): Merge conflict in 1st_file.txt
  Automatic merge failed; fix conflicts and then commit the result.
  ```

* Fix errors and commit changes (Take into account that the other file [not edited one is as if we added it manually])

  ```console
  git add <filename1>
  git commit -m <message>
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git add *
  git_user@Desktop:~/Downloads/git_exercises$ git commit -m "fix error on merge from final to master"
  [master fe7fa06] fix error on merge from final to master
  ```

* Now look at the branch graph

  ```console
  git log --oneline --graph --all
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git log --oneline --graph --all                   
  *   fe7fa06 (HEAD -> master) fix error on merge from final to master
  |\  
  | * 0e3628f (final) Modification of both files
  * | 4bfcefd just a change for conflic purposes
  |/  
  * 158f446 (middle) Adding second file into repogit add 2nd_file.txt
  * 2eab953 My second commit
  * 168d1ca Adding first file to repo

  ```

# Rebasing a branch

* let's go to last branch an merge all changes from master

  ```console
  git checkout <branch_name2>
  git rebase master
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git checkout middle
  Switched to branch 'middle'
  git_user@Desktop:~/Downloads/git_exercises$ git rebase master
  First, rewinding head to replay your work on top of it...
  Fast-forwarded middle to master.

  ```

# Revert changes

* Create a new branch from master, view last commit and delete it. (it should fail since it is a merge)

  ```console
  git checkout master
  git checkout -b <branch_name4>
  git log
  git revert <sha1>
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git checkout -b reverting
  Switched to a new branch 'reverting'
  git_user@Desktop:~/Downloads/git_exercises$ git log
  commit fe7fa066abbca6109bbd8734033c377d5bc6c087 (HEAD -> reverting, middle, master, final)
  Merge: 4bfcefd 0e3628f
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 16:08:42 2019 +0200

      fix error on merge from final to master

  commit 4bfcefd1eefd8b8e9bc8effac1be6717d81acf0c
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 16:05:36 2019 +0200

      just a change for conflic purposes

  commit 0e3628f3c32b17dee534715d081de6f44792ce53
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 15:54:03 2019 +0200

      Modification of both files

  commit 158f44648968305319f1b54eac07701ddb332751
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 14:49:56 2019 +0200

      Adding second file into repogit add 2nd_file.txt

  commit 2eab953c12670c900ecc4ebca34a934dc14061e9
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 14:42:11 2019 +0200

      My second commit

  commit 168d1ca57c43f6b96aa4b145b205533db8b06d3f
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 14:28:29 2019 +0200

      Adding first file to repo
  git_user@Desktop:~/Downloads/git_exercises$ git revert fe7fa066abbca6109bbd8734033c377d5bc6c087
  error: commit fe7fa066abbca6109bbd8734033c377d5bc6c087 is a merge but no -m option was given.
  fatal: revert failed

  ```

* Now let's try with another previous commit and see the differences between branches (this should also give errors that the user should fix).

  ```console
  git revert
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git revert 4bfcefd1eefd8b8e9bc8effac1be6717d81acf0c
  error: could not revert 4bfcefd... just a change for conflic purposes
  hint: after resolving the conflicts, mark the corrected paths
  hint: with 'git add <paths>' or 'git rm <paths>'
  hint: and commit the result with 'git commit'
  ```

* Let's fix the repository to finally revert the changes.

  ```console
  git add <filename1>
  git commit -m <message>
  git log
  ```

  ## command(s) output

  ```console
  git_user@Desktop:~/Downloads/git_exercises$ git add 1st_file.txt
  git_user@Desktop:~/Downloads/git_exercises$ git commit -m "Reverting changes on other branch"
  [reverting 9cc4c81] Reverting changes on other branch
   1 file changed, 1 insertion(+), 2 deletions(-)
  git_user@Desktop:~/Downloads/git_exercises$ git log
  commit 9cc4c8122ac19393bb6aa1c3d3421a1706e4f8e4 (HEAD -> reverting)
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 16:23:33 2019 +0200

      Reverting changes on other branch

  commit fe7fa066abbca6109bbd8734033c377d5bc6c087 (middle, master, final)
  Merge: 4bfcefd 0e3628f
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 16:08:42 2019 +0200

      fix error on merge from final to master

  commit 4bfcefd1eefd8b8e9bc8effac1be6717d81acf0c
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 16:05:36 2019 +0200

      just a change for conflic purposes

  commit 0e3628f3c32b17dee534715d081de6f44792ce53
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 15:54:03 2019 +0200

      Modification of both files

  commit 158f44648968305319f1b54eac07701ddb332751
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 14:49:56 2019 +0200

      Adding second file into repogit add 2nd_file.txt

  commit 2eab953c12670c900ecc4ebca34a934dc14061e9
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 14:42:11 2019 +0200

      My second commit

  commit 168d1ca57c43f6b96aa4b145b205533db8b06d3f
  Author: testrobot <test@test.com>
  Date:   Sun Sep 8 14:28:29 2019 +0200

      Adding first file to repo

  ```

## Git - Notes
### Alan T. Arnholt







Last compiled Tuesday, February 04, 2014 - 8:26:45 PM.

Download and install the lastest version of [Git.](http://git-scm.com/downloads)

<img class=center src="./images/GitDownload.png" height='480'/>

## Mac Users
Install the downloaded file by clicking on the downloaded `*.dmg` file then clicking on the `*.pkg` file. 

<img class=center src="./images/MacGitDownload.png" height='200'/>

If you get a message indicating the file is from an untrusted source, ignore the warning and click on the **Open** button.  If there is no option to **Open**, hold down the CTRL key, select `*.pkg` file, then choose *Open With -> Installer (default)*.

## Windows users

Once the download is complete, right click on the downloaded file to install it as an 
administrator.  Use the default options at each step of the installation if you are unsure 
what you are doing.  When the installation arrives at the screen adjusting your PATH 
environment, click in the circle to the left of **Run Git from the Windows Command Prompt**.


## Initial Setup

If you have never used git before, you need to do some setup first.  Run the following
commands so that git knows your name and email.  The commands are all issued in the
Terminal (Mac) or at the command prompt of Git Bash (Windows).  The Terminal 
application is usually found in `/applications/Utilities`. A quick way to open a 
**terminal** window is by clicking on the magnifying glass icon and typing *terminal* in spotlight.  

<img class=center src="./images/Spotlight.png" height='200'/>

By clicking on the Terminal application, a Terminal window will open.

<img class=center src="./images/TerminalWindow.png" height='150'/>

To open Git Bash, click on the *Windows icon -> Git -> Git Bash*.  The program is most likely located in the Git directory within your Start Menu (or the directory into which Git was installed).

<img class=center src="./images/WindowsProgramGitBash.png" height='400'/>

By clicking on the Git Bash icon, a window similar to the one below will open.

<img class=center src="./images/GitBashWindow.png" height='150'/>

## Run these commands


```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@whatever.com"
git config --global color.ui true
```


If you do not want to type your username and password every time you work with a remote server, you will to install the credential helper.  See the article [Set Up Git](https://help.github.com/articles/set-up-git#platform-all) for additional details on setting up the credential helper.

To confirm your username and email, type `git config --list` at the $ prompt.


```bash
git config --list
```

```
core.symlinks=false
core.autocrlf=true
color.diff=auto
color.status=auto
color.branch=auto
color.interactive=true
pack.packsizelimit=2g
help.format=html
http.sslcainfo=/bin/curl-ca-bundle.crt
sendemail.smtpserver=/bin/msmtp.exe
diff.astextplain.textconv=astextplain
rebase.autosquash=true
user.name=Alan Arnholt
user.email=arnholtat@appstate.edu
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.symlinks=false
core.ignorecase=true
core.hidedotfiles=dotGitOnly
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
remote.origin.url=https://github.com/alanarnholt/STT4870.git
branch.master.remote=origin
branch.master.merge=refs/heads/master
```


From the third line of the previous output, one can see the `credential.helper` is 
being used. 

### Creating a GitHub Account

Point your browser to [https://github.com](https://github.com),
type a username in the `Pick a username` box (please use `firstlast`, for example my username is `alanarnholt`), enter your email (use your school email) in the `Your email` box, type in your password in the `Create a password` box. Then, click the `Sign up for GitHub` box and you will have a GitHub account.


### Creating a GitHub Repository

In order to push your local work to a remote repository, you will first need to create
the remote repository. Log in to your GitHub account, click the `New repository` button,
then give your repository a name and optionally a description.  When you finish, click 
the `Create repository` button, and your GitHub repository will be created.  
![AlansGitRepo](./images/CreateGitRepo.png)


This document is stored in the repository [https://github.com/alanarnholt/STT4870](https://github.com/alanarnholt/STT4870) in the folder [https://github.com/alanarnholt/STT4870/Git](https://github.com/alanarnholt/STT4870/Git). 

## Local Repositories

It is possible to set up a local repository using GUI (drop, drag, etc.) commands or to
use the command line.  I keep my repositories in a folder called *git_repositories* that
is a subfolder of my *USERNAME* directory.  Once you have a local folder with files you
would like to place under version control, use the `git init` command from your working
directory to track your files.  If you clone a remote repository to your machine, you 
will not need to initialize your directory.  One way to clone this repo using `RStudio` is 
to click on File -> New Project 

![NewProject](./images/NewProject.png)

Click Version Control and a new window such as the one below will appear where you will select Git.

![VersionControl](./images/VersionControl.png)

In the next window that appears, which is shown below, enter the URL for the repository you are cloning.  Enter a project name and specify where you want the project to reside on your computer.  When you are finished, click the `Create Project` button and you will have cloned a remote repository.

![ProjectVersionControl](./images/ProjectVersionControl.png)


To check the current status of your repository type:

```bash
git status
```

```
On branch master
Your branch is up-to-date with 'origin/master'.

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   GitOne.Rmd
	deleted:    cache/GITsetup_b0c970510ef94c7a948b007d4995e2c2.RData
	deleted:    cache/GITsetup_b0c970510ef94c7a948b007d4995e2c2.rdb
	deleted:    cache/GITsetup_b0c970510ef94c7a948b007d4995e2c2.rdx
	deleted:    cache/verify_f81c0bc60aa03951091d1db4b41e9fca.RData
	deleted:    cache/verify_f81c0bc60aa03951091d1db4b41e9fca.rdb
	deleted:    cache/verify_f81c0bc60aa03951091d1db4b41e9fca.rdx

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	cache/GITsetup_1e85974789856654fd6170253d9fcbe2.RData
	cache/GITsetup_1e85974789856654fd6170253d9fcbe2.rdb
	cache/GITsetup_1e85974789856654fd6170253d9fcbe2.rdx
	cache/verify_2d584a4c99894e4c308ba44967920be7.RData
	cache/verify_2d584a4c99894e4c308ba44967920be7.rdb
	cache/verify_2d584a4c99894e4c308ba44967920be7.rdx

no changes added to commit (use "git add" and/or "git commit -a")
```

The `git status` shows us what files are not staged for a commit.  Before files can be
committed, they must be added to the staging area.  Files are added to the stating area
with the command `git add file_name`.  To add all files in the working directory, one
can use `git add .`  Next, all files are added to the staging area, and a snapshot is 
taken of the commit with the message "staging all files."

```bash
git add .
git commit  -m "staging all files"
```

```
[master a254aa7] staging all files
 10 files changed, 1 insertion(+), 1 deletion(-)
 create mode 100644 Git/cache/GITsetup_1e85974789856654fd6170253d9fcbe2.RData
 create mode 100644 Git/cache/GITsetup_1e85974789856654fd6170253d9fcbe2.rdb
 create mode 100644 Git/cache/GITsetup_1e85974789856654fd6170253d9fcbe2.rdx
 create mode 100644 Git/cache/STATUS_c084c907b84567e22073c1b7e27f7062.RData
 create mode 100644 Git/cache/STATUS_c084c907b84567e22073c1b7e27f7062.rdb
 create mode 100644 Git/cache/STATUS_c084c907b84567e22073c1b7e27f7062.rdx
 create mode 100644 Git/cache/verify_2d584a4c99894e4c308ba44967920be7.RData
 create mode 100644 Git/cache/verify_2d584a4c99894e4c308ba44967920be7.rdb
 create mode 100644 Git/cache/verify_2d584a4c99894e4c308ba44967920be7.rdx
```


Check the status after the last commit.

```bash
git status
```

```
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	deleted:    cache/ADD_540999b9c1daaa4c31ccd2c535b3e499.RData
	deleted:    cache/ADD_540999b9c1daaa4c31ccd2c535b3e499.rdb
	deleted:    cache/ADD_540999b9c1daaa4c31ccd2c535b3e499.rdx
	deleted:    cache/GITsetup_b0c970510ef94c7a948b007d4995e2c2.RData
	deleted:    cache/GITsetup_b0c970510ef94c7a948b007d4995e2c2.rdb
	deleted:    cache/GITsetup_b0c970510ef94c7a948b007d4995e2c2.rdx
	deleted:    cache/STATUS_c69090ea171fdc61120b83150e1ec346.RData
	deleted:    cache/STATUS_c69090ea171fdc61120b83150e1ec346.rdb
	deleted:    cache/STATUS_c69090ea171fdc61120b83150e1ec346.rdx
	deleted:    cache/verify_f81c0bc60aa03951091d1db4b41e9fca.RData
	deleted:    cache/verify_f81c0bc60aa03951091d1db4b41e9fca.rdb
	deleted:    cache/verify_f81c0bc60aa03951091d1db4b41e9fca.rdx

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	cache/ADD_37d613968d89bfc0fc573bd5f4d62239.RData
	cache/ADD_37d613968d89bfc0fc573bd5f4d62239.rdb
	cache/ADD_37d613968d89bfc0fc573bd5f4d62239.rdx

no changes added to commit (use "git add" and/or "git commit -a")
```

Push changes to the remote repository. 

```bash
git push
```

See if there is anything left to do.

```bash
git status
```

```
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	deleted:    cache/ADD_540999b9c1daaa4c31ccd2c535b3e499.RData
	deleted:    cache/ADD_540999b9c1daaa4c31ccd2c535b3e499.rdb
	deleted:    cache/ADD_540999b9c1daaa4c31ccd2c535b3e499.rdx
	deleted:    cache/GITsetup_b0c970510ef94c7a948b007d4995e2c2.RData
	deleted:    cache/GITsetup_b0c970510ef94c7a948b007d4995e2c2.rdb
	deleted:    cache/GITsetup_b0c970510ef94c7a948b007d4995e2c2.rdx
	deleted:    cache/PUSH_ccaa07cffd798cbbde965296b32e8be8.RData
	deleted:    cache/PUSH_ccaa07cffd798cbbde965296b32e8be8.rdb
	deleted:    cache/PUSH_ccaa07cffd798cbbde965296b32e8be8.rdx
	deleted:    cache/STATUS2_5e0c7941154f2f6f6d64705c7f833e80.RData
	deleted:    cache/STATUS2_5e0c7941154f2f6f6d64705c7f833e80.rdb
	deleted:    cache/STATUS2_5e0c7941154f2f6f6d64705c7f833e80.rdx
	deleted:    cache/STATUS_c69090ea171fdc61120b83150e1ec346.RData
	deleted:    cache/STATUS_c69090ea171fdc61120b83150e1ec346.rdb
	deleted:    cache/STATUS_c69090ea171fdc61120b83150e1ec346.rdx
	deleted:    cache/verify_f81c0bc60aa03951091d1db4b41e9fca.RData
	deleted:    cache/verify_f81c0bc60aa03951091d1db4b41e9fca.rdb
	deleted:    cache/verify_f81c0bc60aa03951091d1db4b41e9fca.rdx

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	cache/ADD_37d613968d89bfc0fc573bd5f4d62239.RData
	cache/ADD_37d613968d89bfc0fc573bd5f4d62239.rdb
	cache/ADD_37d613968d89bfc0fc573bd5f4d62239.rdx
	cache/PUSH_4a4f909daa6525f7416b0e0df208f325.RData
	cache/PUSH_4a4f909daa6525f7416b0e0df208f325.rdb
	cache/PUSH_4a4f909daa6525f7416b0e0df208f325.rdx
	cache/STATUS2_8ac7feaeff926fc5b62fe3cb6b50f859.RData
	cache/STATUS2_8ac7feaeff926fc5b62fe3cb6b50f859.rdb
	cache/STATUS2_8ac7feaeff926fc5b62fe3cb6b50f859.rdx

no changes added to commit (use "git add" and/or "git commit -a")
```

Show the last three commits with

```bash
git log  -3
```

```
commit a254aa74912df2f0585b0228fc5ae5fdd7dec68d
Author: Alan Arnholt <arnholtat@appstate.edu>
Date:   Tue Feb 4 20:26:46 2014 -0500

    staging all files

commit 750534b273512236cc04de715f01bff1a1eafdd5
Author: Alan Arnholt <arnholtat@appstate.edu>
Date:   Tue Feb 4 20:16:26 2014 -0500

    running engine = "sh" from home because my machine can not find "bash" ---UGH!---rerun at office with engine = "bash"

commit b609bf0da0ef7a7d4eedc4874e35515c1c2c4678
Author: Alan Arnholt <arnholtat@appstate.edu>
Date:   Tue Feb 4 20:12:01 2014 -0500

    who knows
```


That was ugly. Let us try some formatting.


```bash
git log --pretty=oneline -3
```

```
a254aa74912df2f0585b0228fc5ae5fdd7dec68d staging all files
750534b273512236cc04de715f01bff1a1eafdd5 running engine = "sh" from home because my machine can not find "bash" ---UGH!---rerun at office with engine = "bash"
b609bf0da0ef7a7d4eedc4874e35515c1c2c4678 who knows
```


The previous output was to brief to suit me.  Let us try some further formatting.


```bash
git log --pretty=format:"%h %ad- %s [%an]" -3
```

```
a254aa7 Tue Feb 4 20:26:46 2014 -0500- staging all files [Alan Arnholt]
750534b Tue Feb 4 20:16:26 2014 -0500- running engine = "sh" from home because my machine can not find "bash" ---UGH!---rerun at office with engine = "bash" [Alan Arnholt]
b609bf0 Tue Feb 4 20:12:01 2014 -0500- who knows [Alan Arnholt]
```


Maybe even some statistics?


```bash
git log --pretty=format:"%h %ad- %s [%an]" -3 --stat
```

```
a254aa7 Tue Feb 4 20:26:46 2014 -0500- staging all files [Alan Arnholt]
 Git/GitOne.Rmd                                            |   2 +-
 Git/cache/GITsetup_1e85974789856654fd6170253d9fcbe2.RData | Bin 0 -> 199 bytes
 Git/cache/GITsetup_1e85974789856654fd6170253d9fcbe2.rdb   |   0
 Git/cache/GITsetup_1e85974789856654fd6170253d9fcbe2.rdx   | Bin 0 -> 113 bytes
 Git/cache/STATUS_c084c907b84567e22073c1b7e27f7062.RData   | Bin 0 -> 537 bytes
 Git/cache/STATUS_c084c907b84567e22073c1b7e27f7062.rdb     |   0
 Git/cache/STATUS_c084c907b84567e22073c1b7e27f7062.rdx     | Bin 0 -> 113 bytes
 Git/cache/verify_2d584a4c99894e4c308ba44967920be7.RData   | Bin 0 -> 498 bytes
 Git/cache/verify_2d584a4c99894e4c308ba44967920be7.rdb     |   0
 Git/cache/verify_2d584a4c99894e4c308ba44967920be7.rdx     | Bin 0 -> 113 bytes
 10 files changed, 1 insertion(+), 1 deletion(-)

750534b Tue Feb 4 20:16:26 2014 -0500- running engine = "sh" from home because my machine can not find "bash" ---UGH!---rerun at office with engine = "bash" [Alan Arnholt]
 Git/GitOne.Rmd  | 16 +++++++++-------
 Git/GitOne.html | 18 ++++++++++--------
 Git/GitOne.md   | 18 ++++++++++--------
 3 files changed, 29 insertions(+), 23 deletions(-)

b609bf0 Tue Feb 4 20:12:01 2014 -0500- who knows [Alan Arnholt]
 Git/cache/LOGP2_faf1a7fcf18137324c7c98647d730ea6.RData   | Bin 273 -> 0 bytes
 Git/cache/LOGP2_faf1a7fcf18137324c7c98647d730ea6.rdb     |   0
 Git/cache/LOGP2_faf1a7fcf18137324c7c98647d730ea6.rdx     | Bin 113 -> 0 bytes
 Git/cache/LOGP3_ad807c34590b81f628e6cb6032102919.RData   | Bin 437 -> 0 bytes
 Git/cache/LOGP3_ad807c34590b81f628e6cb6032102919.rdb     |   0
 Git/cache/LOGP3_ad807c34590b81f628e6cb6032102919.rdx     | Bin 113 -> 0 bytes
 Git/cache/LOGP_85b7cbcb21a72630e78bd3b750ea156f.RData    | Bin 267 -> 0 bytes
 Git/cache/LOGP_85b7cbcb21a72630e78bd3b750ea156f.rdb      |   0
 Git/cache/LOGP_85b7cbcb21a72630e78bd3b750ea156f.rdx      | Bin 113 -> 0 bytes
 Git/cache/LOG_087011b0f8f69f16e2c2e5605086c615.RData     | Bin 343 -> 0 bytes
 Git/cache/LOG_087011b0f8f69f16e2c2e5605086c615.rdb       |   0
 Git/cache/LOG_087011b0f8f69f16e2c2e5605086c615.rdx       | Bin 113 -> 0 bytes
 Git/cache/PUSH_4a4f909daa6525f7416b0e0df208f325.RData    | Bin 121 -> 0 bytes
 Git/cache/PUSH_4a4f909daa6525f7416b0e0df208f325.rdb      |   0
 Git/cache/PUSH_4a4f909daa6525f7416b0e0df208f325.rdx      | Bin 113 -> 0 bytes
 Git/cache/STATUS2_8ac7feaeff926fc5b62fe3cb6b50f859.RData | Bin 687 -> 0 bytes
 Git/cache/STATUS2_8ac7feaeff926fc5b62fe3cb6b50f859.rdb   |   0
 Git/cache/STATUS2_8ac7feaeff926fc5b62fe3cb6b50f859.rdx   | Bin 113 -> 0 bytes
 Git/cache/STATUS3_12105d35cf1bc9dd32a9a4e2704fe895.RData | Bin 589 -> 0 bytes
 Git/cache/STATUS3_12105d35cf1bc9dd32a9a4e2704fe895.rdb   |   0
 Git/cache/STATUS3_12105d35cf1bc9dd32a9a4e2704fe895.rdx   | Bin 113 -> 0 bytes
 Git/cache/STATUS_c084c907b84567e22073c1b7e27f7062.RData  | Bin 699 -> 0 bytes
 Git/cache/STATUS_c084c907b84567e22073c1b7e27f7062.rdb    |   0
 Git/cache/STATUS_c084c907b84567e22073c1b7e27f7062.rdx    | Bin 113 -> 0 bytes
 Git/cache/Systime_7b042452f5d04aa760cf4ad34f0b08ee.RData | Bin 104 -> 0 bytes
 Git/cache/Systime_7b042452f5d04aa760cf4ad34f0b08ee.rdb   | Bin 73 -> 0 bytes
 Git/cache/Systime_7b042452f5d04aa760cf4ad34f0b08ee.rdx   | Bin 130 -> 0 bytes
 Git/cache/verify_2d584a4c99894e4c308ba44967920be7.RData  | Bin 368 -> 0 bytes
 Git/cache/verify_2d584a4c99894e4c308ba44967920be7.rdb    |   0
 Git/cache/verify_2d584a4c99894e4c308ba44967920be7.rdx    | Bin 113 -> 0 bytes
 30 files changed, 0 insertions(+), 0 deletions(-)
```


Now, just to show how cool this is, we will mix in a little `R`.


```r
library(ggplot2)
ggplot(data = CO2, aes(x = Type, y = uptake, fill = Type)) + geom_boxplot() + 
    facet_grid(Treatment ~ .) + theme_bw()
```

<img src="figure/Rgraph.png" title="plot of chunk Rgraph" alt="plot of chunk Rgraph" style="display: block; margin: auto;" />


I love graphs!  The following graph created with `ggplot2` uses Greek letters in
the facet panels.  

<img src="figure/ggplot2Graphs.png" title="plot of chunk ggplot2Graphs" alt="plot of chunk ggplot2Graphs" style="display: block; margin: auto;" />


### So you want to collaborate?

At this point, you have forked a repo and would like to contribute to
someone's project.  A great place to start is by reading [https://help.github.com/articles/using-pull-requests](https://help.github.com/articles/using-pull-requests).
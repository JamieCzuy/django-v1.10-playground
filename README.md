# django-v1.10-playground
Playground for Django v1.10 (using Python 3.6)

# Setup

## Install / Upgrade Python3
[Python 3.6](https://docs.python.org/release/3.6.0/) is now out (as of 2016-12-23) so make sure you are using that version of Python.

I have installed /upgraded Python3 using [homebrew](http://brew.sh/):
```
brew install python3
brew upgrade python3
python3 --version
# Python 3.6.0
```


## Create a Python Virtual Environment
Ever since Python 3.5 [venv](https://docs.python.org/3/library/venv.html) is the recommended tool for creating virtual environmets.
Use `venv` to create a virtual environment for your Django Tutorial code:
```
# You can name the environment whatever you like
# (a subfolder is created in the current folder to hold your new virutal environment)
python3 -m venv django-playground
```


## Activate the Virtual Environment
To activate the virtual environment you need to [source](http://superuser.com/a/46149) the activate file (which was created in then virtual environment's bin folder):
```
souce ./django-playground/bin/activate
# You should notice the prompt changes to include the name of your virtual environment
```


## Install Django
Once the virutal environment is activated whatever python packages you install
using `pip` will be installed exclusively for the virtual environment. The python packages are
installed in the virtual environment's `./lib/python3.6/site-packages/` subfolder.

Use pip to install the latest version of Django (from [django quick install guide](https://docs.djangoproject.com/en/1.10/intro/install/)):
```
pip install django
python -m django --version
# 1.10.4
```


## Create GitHub Repo
You should never code without using some kind of version control.
[git](https://git-scm.com/) is the defacto standard and [github](?) is the defacto standard for online repos.

I installed git using [homebrew](http://brew.sh/):
```
brew install git
```

Since this is just tutorial code there should be no problem having the code be in a Public repo.

Follow the directions [here](https://help.github.com/articles/creating-a-new-repository/) 
to create a new public repo named simular to your project name. Choose to include a README and a .gitignore file for the Python language.


## Clone The Repo
Activate you virtual environment and change to the virtual environment's folder:
```
source <virtual environment folder>/bin/activate
cd $VIRTUAL_ENV
```

Get the url for cloning using ssh from github and use it
with [git clone](https://git-scm.com/docs/git-clone) to clone the repo
into a new `work` subfolder in the virtual environment folder:
```
git clone git@github.com:<YOUR_GITHUB_NAME>/<YOUR_GITHUB_REPO>.git work
cd work
ls -l
# README.md
```


## Make Your First Commit
Edit the README file and add a description.

I use [vim](http://www.vim.org/) as my coding editor.
I installed it using [homebrew](http://brew.sh/):
```
brew install vim
```

Note the README is a [markdown](https://daringfireball.net/projects/markdown/syntax) file in [GitHub flavored Markdown](https://guides.github.com/features/mastering-markdown/)
```
vim README.md
# Edit the file - add a description
```

Use [git status](https://git-scm.com/docs/git-status) to verify that the README is the only file changed.
```
git status
# modified: README.md (in red)
```

Use [git diff](https://git-scm.com/docs/git-diff) to verify that the changes you made were what you wanted:
```
git diff
# Should see changes made to the README.md file
```

If the changes look good then use [git add](https://git-scm.com/docs/git-add) to add the files to the index before you commit:
```
git add .
```

Use [git status](https://git-scm.com/docs/git-status) again to see that the README.md is now ready to be committed:
```
git status
# modified: README.md (in green)
```

Now use [git commit](https://git-scm.com/docs/git-commit) with a message to commit the changes:


**Note about commit messages:** You should always include a real commit message
and it should have two parts: "Type: Message". The Type should describe the
type of changes being committed. For example Type should be: "Doc", "Fix",
"Feature", "Refactor", "DevOps" (for infrastructure as code changes), "Test"

The message should be what the commit does to the system.
The message should be written in such a way that this statement makes
sense: "Apply this commit to " + Message.
So for your first commit could have a message such as: "Doc: Add a description to the README.md"
Which would read like: "Apply this commit to *Add a description to the README.md file*"
```
git commit -m "Doc: Add a description to the README.md file"
```

At this point your changes have been committed to your local repo.
To share the changes with the rest of the team we need to copy the changes to the remote repo.

First use [git remote](https://git-scm.com/docs/git-remote) to verify that your local repo is connected
to the correct remote repo:
```
git remote -v
# Should be your github repo for both getting changes from (fetch) and pushing changes to (push)
```

Now use [git pull](https://git-scm.com/docs/git-pull) to check that no one
else has made any changes to the repo.
Of course for this repo you are the only developer so it is not neccessary
but it is a good habit to get into: `pull before you try to push`:
```
git pull
# Already-up-to-date
```

At this point your changes have been committed to your local repo and you know there are no conflicts in the remote repo (that is what `git pull` told us). Now use [git push](https://git-scm.com/docs/git-push) to push the changes up to GitHub to share with the rest of your team.
```
git push
# Info about the changes
# < source commit >..< new commit > master -> master
```

Now no matter what happens locally you can always go back into the repo on GitHub and return to how your folder is at this point. Or you can go to a different machine to work and recreate this folder.


**NOW WE ARE READY TO START THE DJANGO TUTORIAL**


Create a new repository from the command line. Please note that you need to create the repository in Github first, then proceed with the following:

```shell
echo "# repo name" >> README.md
git init
git add README.md
git commit -m 'first commit'
git branch -M master
git remote add origin 'repo-name'
git push -u origin HEAD:master
```

or alternatively push to an existing repo from the command line

```shell
git remote add origin 'repo-name.git'
git branch -M master
git push -u origin HEAD:master
```

Or you can take the most simplest way to create a repo is to create a repo, copy the url to the clipboard and in the terminal type the following:

```shell
git clone 'git_url/repo-name.git'
```

This command should clone a the repositiory for you.
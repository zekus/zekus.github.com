---
date: '2009-10-12 23:55:28'
layout: post
slug: super-easy-git-remote-repository
status: publish
title: 'super-easy Git remote repository '
wordpress_id: '245'
categories:
- GIT
---

## 1. Creating a remote repository before the local one


**Step 1**: create the folder on the remote server and initialise the empty bare repository
```
ssh username@yourserver
mkdir yourgitremoterepo.git
cd yourgitremoterepo.git
git --bare init
```
**Step 2**: back to your machine, clone the repository
```
git clone username@yourserver:yourgitremoterepo.git
```


## 2. Making your existing local repository available on remote


**Step 1:** I assume that you have done something like this
```
cd yourlocalrepo
git init
git add .
git commit -a -m "first commit"
```
**Step 2:** to create the remote repository, login to your remote server and initialise an empty bare repository
```
ssh username@yourserver
mkdir yourgitremoterepo.git
cd yourgitremoterepo.git
git --bare init
```
**Step 3: **now back to your machine, link your remote repository with the local one and push all your files
```
git remote add origin username@yourserver:yourgitremoterepo.git
git push origin master
```

done!

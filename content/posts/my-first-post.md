---
title: "Installing Hugo"
date: 2022-06-19T11:26:36+02:00
draft: false
---




## About

Since I am not prepared, I thought I'd document for myself how this blog has been setup.
I am using hugo.io as a static site generator, because it is fast, widely used and good enough for me.

This is very well documented here: https://gohugo.io/getting-started/quick-start/


## Installation

Hugo can be installed on Mac, Linux and Windows.

To install it on windows with choco (an excellent windows package manager) already installed, just use
> choco install hugo -confirm


## Create a new Site

Execute

> hugo new site quickstart

which will create a new folder "quickstart" and the required files.


## Add a theme

Hugo supports different themes. You can use existing ones or create your own.

We will add an existing one via a git submodule.
To add a theme, go into the newly created directory
> cd quickstart

Initialize git sourcecontrol in the root directory
> git init

and add the ananke theme via a git submodule:
> git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke

Finally we need to tell Hugo to use the theme. For that create a config.toml file in the root directory (if not already present) and open it with your texteditor.
Add a line:
> theme = 'ananke'

to it and save it. You can also edit other settings via the config.toml file (base url, etc).


## Add a blog entry

To write your first article, execute the following command:

> hugo new posts/my-first-post.md

This will create a draft file. Open the file posts/my-first-post.md with your texteditor. You can modify some parameters/metadata in the top section of the file.
Write some markdown for your blog itself.


## Start blog locally
To see your blog locally enter the following command to start hugo in development mode, which renders your blog entry (new articles are drafts by defualt and only visible locally):
> hugo server -D

## Build the blog

After you have inspected your blog articles and you are happy with it, you need to make the article public by  setting the draft in the article file itself:
> draft: false

After that you need to build the whole blog:
> hugo -D

This will compile all assets and the generated output will be in the public directory (this is a default and can be changed - see hugo documentation if you want to do so).
You may want to publish this public directory by uploading it manually e.g. via SFTP to your webhost, have a build pipeleine or another way.

## Committing the changes to sourcecontrol

After you created everything, you might also want to commit and push your changes to sourcecontrol.
This helps you to version your blog, check changes, alter on automate publishing/releases of your blog etc.

To commit your changes locally run:
> git commit -m "Added first blog post"
To push your changes to the git repository, run
> git push

Info: you need to setup the remote server first that hosts your code. There are several hosts you can use - most people use github.
Please check some articles that describe how to work with git:
https://docs.github.com/en/get-started/quickstart/git-and-github-learning-resources

https://www.w3schools.com/git/default.asp


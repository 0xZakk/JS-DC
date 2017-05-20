# The Command Line

- Welcome to Class
- Go over the Learning Objectives

## The Terminal

### Introduction
- What is the terminal?
  - Terminal = Command Line = Console
  - Terminal is a tool for us to navigate the file system on our computer
  - Predates the GUI (i.e. Finder on a Mac or Explorer on a PC)
  - Character User Interface
- Why might we use it?
  1. It's concise and powerful - you can do a lot with relatively few keystrokes,
  2. It's efficient - both as a use of time and for your machine, because it requires fewer resources,
  3. It's expert-friendly - which is to say that if you invest a little time in getting good at using the command line, the productivity benefits that you'll reap are incredible,
  4. It's easy to automate via scripting - you can write scripts that will handle repetitive tasks.

For Macs:
- Open the "Terminal" app (Applications > Utilities > Terminal)

For Windows:
- Open the "Git BASH" application

### Anatomy of the Terminal
- prompt
- command
- input
- flags/Options
- output

### Navigating our File System
- start by figuring out where we are now:
  - print working directory - `pwd`
  - *absolute path*
  - *root dir `~/`*
- now we know where we are, lets go somewhere. Where can we go from here?
  - list contents - `ls`
  - list all directories in the current folder
  - what's a directory?
- check pace
- lets open one of these folders
  - change directories - `cd`
  - change to (a) a specific folder, (b) go up a folder, (c) go up more than one folder, (d) go to the home folder
- navigating folders is super useful, but you guys probably don't have that many yet - so lets make some
  - make directory - `mkdir`

## Activity: Terminal Review
- Count off 1-4 and find a corner of the room
- A question or command will come up on the board
- Go around your group answering the question or explaining what the command does

## Git and GitHub
- Last class we installed something called Git and we made you all get accounts on something called GitHub before this course started
- What are these?

#### A Brief Introduction
- Git:
  - A version control system
  - not so different from track changes in Microsoft word, but a lot more powerful
  - the goal of a version control system is to allow multiple people to work on the same code base easily, keeping track of everyone's changes and the history of all those changes
- Github
  - Saas platform for working with git

#### Workflow
*Draw this on the board*

### Creating a Repository
- create a new repository using git init
- add a file to a repository
- commit those changes
- create a new repository on GitHub
- push your changes to Github

*Maybe take a break around this point*

### Forking a Repository
- pair up wit the person sitting next to you
- have them slack you the link to their repository and slack them the link to yours
- Once you've opened the repository in github

### Cloning a Repository
- Copy the link for the repository
- in the command line, clone the repository to a new directory

### Making a Pull Request
- push your changes to origin of the forked repository
- go to the github.com for the forked repository and navigate back to the original repository
- click on 'Pull Request', then 'New' to create a pull request. Give it a title and then write a message describing the changes you made.
- Go back to your own repository and check the pull request. Go ahead and merge it in

### Working with upstream
- pull down the changes your partner made using `git pull`
- make a change to `index.js` and push it up to your origin
- now switch to your clone of your partner's repository
- navigate to the github.com page for your partners repo and copy the link
- switching back to the command line, add the repository as upstream by running `git remote add upstream https://github.com/username/repository`
- now run `git pull upstream master` to synchronize their changes with yours, and push them to your remote origin.

## Class Work
- we have a repository for this class which contains all the lesson notes, the slides and your homework assignments
- You'll want to fork this repository and clone your fork locally so that you can (1) follow along and (2) do your homework
- you'll submit your homework before every class by making a pull request
- I would make a directory at the root level of your user called `projects` or `dev` or something like that. Then create a folder there called `ga` or `general-assembly` and clone your fork of the repository into that folder as `js-dc-4`.


## Activity: Scavenger Hunt
https://github.com/ga-students/js_dc_scavenger_hunt

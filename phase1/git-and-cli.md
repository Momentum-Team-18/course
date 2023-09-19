---
layout: topic
title: 'Developer Tools: the Command Line and Git'
topic: The Command Line and Git
category: phase1
parent: Phase 1 HTML and CSS
nav_order: 1
published: true
---

## 🎯 Objectives

- Orientation
- Setting up your computer
- Using the command line
- Git & GitHub

## 🏗️ Today's Project: Git It

Complete [Git-It]({{site.data.phase1.projects.git_it.url}}), a tutorial program that will walk you through the basics of Git and GitHub. This project is due {{site.data.phase1.projects.git_it.due_date | date: "%A, %B %e" }}.

To install it and its dependencies, open a terminal and run:

`sudo apt install libgconf-2-4 libcanberra-gtk-module`

`wget https://github.com/jlord/git-it-electron/releases/download/4.4.0/Git-it-Linux-x64.zip`

`unzip Git-it-Linux-x64.zip`

This should put a Git-it executable program inside a Git-it-Linux-x64 directory. You can check by typing `ll Git-it-Linux-x64` - you should see 'Git-it*' in green listed. Run the program by typing: `./Git-it-Linux-x64/Git-it`

Once the application is running, read the instructions and complete the tasks in Git-it. It will take you some time to get all the way through it.

To complete the project, you must submit the link to the pull request that you will create in the second-to-last Git-It task.

Your link should look similar to this, with a different number at the end: `https://github.com/jlord/patchwork/pull/37062`

[Submit the link to your pull request url using this form](https://forms.gle/hKL37abHZ7TEoyWT6) before tomorrow's meeting.

## 🔖 References

- [Computer Setup for Linux-Ubuntu]({% link references/computer-setup-linux.md %})
- [Command Line notes]({{ site.team_notes_repo }}/blob/main/command-line.md)
- [Git notes]({{ site.team_notes_repo }}/blob/main/git.md)

{% include reference_links.md %}

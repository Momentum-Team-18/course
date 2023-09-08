---
layout: topic
title: HTML
parent: Phase 1 HTML and CSS
nav_order: 2
published: true
---

## 🎯 Objectives

- Learn about HTML tags and elements
- Create a page with HTML

## 🏗️ Project

For your first coding project, you will build a small, three-page website using only HTML. With HTML we are concerned with structure and content, not layout or style.

This project is due on {{ site.data.phase1.projects.html_dog_adoption.due_date | date: "%A, %B %e" }}. You submit this project by pushing your code to your project repo on GitHub.

- [Link to the project invitation]({{ site.data.phase1.projects.html_dog_adoption.url }})
- [Quick video showing how to clone your project repo](https://www.loom.com/share/c7871fa5f80f4cbda3dbcce36db68dab)

## How to Get Started with Your Project

We are using a tool called GitHub classroom during this course. For each project, GitHub classroom will generate a repository (repo) on GitHub for each person to work in.

Each day we will share a project invitation here on this page. Clicking on the link will take you to a page where you will see a message that looks something like this:

![]({{ 'assets/images/gh-classroom-accept.png' | relative_url }}){:.img--post}
_* Don't build [Skynet](https://en.wikipedia.org/wiki/Skynet_(Terminator))_{:.img--caption}

You'll see your github username as part of the repo name instead of `your-github-username`. When you accept the project, GitHub will create your project repo and, when it is done, give you a link to it (from now on, this is the link you will use to see your project on GitHub, NOT the project invitation link). Go to that newly created repo and click on the green button to "Clone or download" your repo. This will copy the repo's url to your clipboard. If you want guidance on how to do this, there is a link to a video demo below.

In your terminal, navigate to the folder where you intend to keep your projects. When you are in the directory you want to be in (check with `pwd`!), type `git clone url-for-your-repo`, but in place of `url-for-your-repo`, paste in the url you copied from GitHub. You'll see output indicating the repo is being cloned. When it's done, make sure you `cd` into it and type `git status` to see that you are in a git repo. Open this repo in VS Codium (an easy way to do this is to type `codium .` when you are in the project repo) and do your work here. Add and commit in the terminal as you work.

## Using VS Codium

VS Codium (or Visual Studio Codium) is a code editor made by Microsoft. It is free and open source, and it's used by many professional developers.

See [Getting Started with VS Code](https:// code.visualstudio.com/docs/introvideos/basics) for an overview and a video intro to using this tool.

**NOTE**: The video begins with installation instructions, which you can skip. You installed this already in the computer setup instructions, so you should be able to see an icon for Visual Studio Codium in your `Applications` menu. If you have not installed it yet, go back to the setup instructions and complete that step. We will use VS Codium every day.

## 🔖 References

- [HTML notes]({{ site.team_notes_repo }}/blob/main/html.md)
- [HTML]({% link references/html.md %})
- [Accessibility (a11y)]({% link references/a11y.md %})
- [Asking Questions and Getting Help][help]
- [Using Visual Studio Code][vscode]
- [Git and Command Line References]({% link references/git-and-cli.md %})

{% include reference_links.md %}

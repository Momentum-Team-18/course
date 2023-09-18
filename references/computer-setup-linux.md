# Computer Set-up Instructions Linux-Ubuntu

Getting your tools right is an important step in becoming a developer. This guide will walk you through every step you need to take to be ready to write code at Momentum.

There are multiple options for setting up your computer. This guide is opinionated about those options. Our guidelines are:

- When possible, use what you already have instead of installing something new.
- Use the most common FOSS development tool unless it is deficient.
- Less setup is better.

**These instructions assume that you are setting up a machine with Ubuntu LTS 22.04 installed.**

**Please read carefully and do all the steps.** 

---

## Initial Setup

Make sure you have followed the student_laptop_setup.pdf first!

### Check for additional drivers

Press the super key (windows key) and type “additional drivers” - when the app by that name is highlighted, press enter and wait for the driver list to be downloaded. If there are any needed drivers install them and apply changes - you may be required to reboot the laptop.

### Install multi-media codecs and a player

Open Terminal and run the following command to install a media player and codecs for playing more audio and video formats:

<aside>
⚠️ When you see these commands, **do not paste or type the `$`**. The dollar sign is only there to indicate the terminal prompt, where you start typing.

"Run" means that you type the command and press the `return` or `enter` key.

</aside>

```bash
$ sudo apt install ubuntu-restricted-extras vlc
```

Enter your password then accept the terms for TrueType fonts if/when prompted. Hint: use TAB to highlight the OK button, then hit enter. Use the left arrow to highlight Yes and hit enter to accept the license terms for Microsoft’s font package.

### Install packages needed for this guide

```bash
$ sudo apt install wget curl
```

### Enable Firewall

While still in the terminal type this command to enable ufw:

```bash
$ sudo systemctl enable ufw
```

If you would like to use a GUI to control ufw then use this command to install the app:

```bash
$ sudo apt install gufw
```

---

## Git

[Git](http://git-scm.com/) is the version control tool developers use to manage and track changes to code. You'll learn how to use it on Day One at Momentum, and we will use it every day.

We can install it from the Terminal. Run:

```bash
$ sudo apt install git
```

You can make sure it is installed by running the following. The expected output is shown beneath the command:

```bash

$ git --version
git version 2.34.1 # Note! Yours doesn't have to be this exact same version.
$ which git 
/usr/bin/git
```

### Configuring Git

Git has a configuration file called `.gitconfig` that is located in your home directory (`~/.gitconfig`). It's a "dotfile" which means its name starts with a `.` , it's intended for configuration settings, and it is invisible using the File Browser. On your first day at Momentum, you will learn more about interacting with your computer's file system in the terminal.

We need to configure Git to define your **user** (this should be the same email you will use for GitHub, so replace the placeholder value below with that information):

```bash
$ git config --global user.name "Your Name Here"
$ git config --global user.email "your_email@youremail.com"
```

No output is expected after you run these commands, so don't worry if you don't see confirmation of success. To check that these settings were successful, you can run:

```bash
$ git config -l
# If your configuration above succeeded, you should see the following output:
user.email=your_email@youremail.com
user.name=Your Name Here
```

  

### Configure defaults

Code lives in "repositories" in Git, and is organized in "branches." We need to tell git what to call the **default branch** it makes for any new repository. We'll give it the conventional name "main".

```bash
$ git config --global init.defaultBranch main 
```

Set a default merge strategy for git. This setting tells git to combine branches without overwriting anything. 

```bash
$ git config --global pull.rebase false
```

<aside>
⚡ If you want to check that all of these Git settings are configured correctly, you can use the `git config -l` command to see the values that you set. If anything looks wrong, just run the same `config` command from above again with the correct value.

</aside>

### Configure files to exclude from Git

It is important to tell Git not to include irrelevant files in its tracking system.

For instance, there are files that are only needed by Ubuntu or our Editor and are not relevant to our code. We also want to exclude any other automatically created files that are not necessary for our code but only for those locally installed programs. 

To configure Git to always exclude certain files, we create a global exclude list. The conventional name for this file is the `.gitignore` file.

Specify a global exclusion list:

```bash
 $ git config --global core.excludesfile ~/.gitignore_global
```

Create the global ignore file:

```bash
$ touch ~/.gitignore_global
```

And exclude settings files generated by our code editor:

```bash
$ echo .vscode-oss >> ~/.gitignore_global
```

You won’t see any output from these commands.

## GitHub

GitHub works with Git to allow us to share code with other people. We will use GitHub every day in class, and you'll use it (or similar) throughout your career as a developer.

### 👉 Go to the [GitHub homepage](https://github.com/) and sign up for an account.

Make a note of your password, because you will need it again when you connect to GitHub through your terminal.

<aside>
🤓 Employers will definitely look at your GitHub account, so keep that in mind when you’re choosing a username.

</aside>

Once you have an account you can configure Git to store your GitHub username by running:

```bash
$ git config --global user.username "your GitHub account username"
```

### Set up a secure way to store your credentials

To use GitHub from the terminal, you need to connect to your own GitHub account. To make this easier, we’ll store your credentials on your computer so you won’t have to enter them every time. We’ll use LibSecret Credential Manager to handle this for us. 

Run these Terminal commands to install it:

```bash
$ sudo apt install libsecret-1-0 libsecret-1-dev build-essential
$ cd /usr/share/doc/git/contrib/credential/libsecret
$ sudo make
$ cd
```

You’ll be asked to enter the password for your computer to complete the installation process. 

You don’t need to do anything else right now. The first time you connect to GitHub from the command line in class, you’ll be guided through a process to enter your credentials. They’ll be stored securely on your machine, and you won’t have to enter them again after that, unless you change them.

<aside>
💁🏻 If you see a message in the terminal about creating a personal access token, you should repeat these steps. You should not need a token if your credential manager is set up correctly.

</aside>

---

## Customizing the Command Line

Developers routinely interact with their computer through text commands in the terminal. You'll be spending a lot of time in the terminal. We want to set a few important things at first, but you will likely customize it further as you become more familiar with what your terminal can do and develop your own preferences for it.

### Install bash-completion and neofetch

Run the following:

```bash
$ sudo apt install bash-completion neofetch
```

### Install a font that works well for code

A font is the digital version of a typeface. For code we need a monospaced font, and for some other features we need a font that has icons included in its character set.

Run the following commands to install the monospaced Hack Nerd Font.

```bash
$ mkdir -p ~/.local/share/fonts
$ cd ~/.local/share/fonts && curl -fLO https://github.com/ryanoasis/nerd-fonts/releases/latest/download/Hack.tar.xz
$ tar -xf Hack.tar.xz
```

When it’s done installing, close and reopen the terminal. Then go to **Terminal > Preferences > Profiles > Add.** Name the Profile, then click ‘Custom Font’ and scroll or search for Hack Nerd Font Mono. You can set any other preferences you like here.

<aside>
🤓 You can choose any monospaced font you like. Here are some to choose from: **[Nerd Fonts](https://www.nerdfonts.com/)**

</aside>

---

## Node.js

When we work with JavaScript, we will often need to use tools written with Node.js. 

To install Node, run (make sure you type/copy the final dash in this command):

```bash
$ curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash -
```

You will see a script deprecation warning - do not worry, this doesn’t apply to us right now. Wait 60 seconds and the script will run. Then install node:

```bash
$ sudo apt install nodejs
```

Once this is done, you should have Node.js and the package manager that we’ll use with it, npm, installed (npm is included with the Node.js installation).

Run the following commands to check that you successfully installed Node and npm:

```bash
$ node --version
v18.17.1

$ npm --version
	9.6.7
```

---

## Install Desktop Apps

### Visual Studio Codium for writing code

Every developer needs a good text editor to write code. There are a lot of different ones you could use, but the one we will teach you to use is an industry standard used by many professionals today. [Visual Studio Codium](https://vscodium.com) (or VSCodium) is a free (as in freedom) and open source program.

To install it, run: 

```bash
$ wget -qO - https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/raw/master/pub.gpg \
    | gpg --dearmor \
    | sudo dd of=/usr/share/keyrings/vscodium-archive-keyring.gpg
```

```bash
$ echo 'deb [ signed-by=/usr/share/keyrings/vscodium-archive-keyring.gpg ] https://download.vscodium.com/debs vscodium main' \
    | sudo tee /etc/apt/sources.list.d/vscodium.list
```

```bash
$ sudo apt update && sudo apt install codium
```

Once you have this installed, we’ll configure Git to use VSCodium as your default text editor when Git requires you to type in a message. 

```bash
$ git config --global core.editor "codium --wait"
```

---

### Add Git information in your prompt

It's important to run all of these lines in this order. You will have better results if you copy and paste instead of trying to type these lines out. Remember not to include the dollar sign if you copy and paste!

```bash
$ cd ~/.config
$ wget https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh
$ chmod +x git-prompt.sh
$ cd ~
$ codium .bashrc 
```

The last command will open your bash config file (.bashrc) in your code editor, VSCodium. Scroll down to the bottom of the file and add these lines:

```bash
. ~/.config/git-prompt.sh
export GIT_PS1_SHOWDIRTYSTATE=1
export PS1='\w$(__git_ps1 " (%s)")\$ '
neofetch
```

Save the file (Ctrl+S) and close the program. Back in the terminal run:

```bash
. .bashrc
```

If all went well you should see ASCII art plus system details and your prompt should now look like:

```bash
~$
```

### Chromium for a web browser

Chromium is the open source base of many browsers, including Chrome, Edge, Brave, and many more. We will use Chromium for testing our front-end. To install it run:

```bash
$ sudo add-apt-repository ppa:xtradeb/apps -y
$ sudo apt update && sudo apt install chromium
```

---

### Slack for communicating with teammates

We use [Slack](https://slack.com/help) for communicating with each other at Momentum. It’s a live chat tool that allows us to send and receive real-time messages.

Open Chromium and visit this url: [https://slack.com/downloads/linux](https://slack.com/downloads/linux) - under the demo screenshot find and click on ‘Download .DEB app’ - keep track of where it downloads, likely your Downloads folder.

Back in the Terminal run this command (assuming you saved slack version 4.33.90 to the Downloads folder, adjust the file path and version as necessary):

```bash
$ cd ~/Downloads
$ sudo apt install ./slack-desktop-4.33.90-amd64.deb
```

When this is done you’ll see the Slack icon in your Applications menu.

---

### Zoom for video meetings

You can [get a free account for Zoom](https://zoom.us/signup#/signup) and run video meetings using the desktop app. 

```bash
$ wget https://zoom.us/client/5.15.10.6882/zoom_amd64.deb
$ sudo apt install ./zoom_amd64.deb
```

When this is done you’ll see the Zoom icon in your Applications menu.

---

# 🎉 Done!

Your computer is set up and ready to go.
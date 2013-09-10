Bungler
=========

Because you're so damn tired of `bundle exec` every time you do anything with your rails project.

#### Why the face?
Other solutions I've come across include bash alias, or security nightmares like `export PATH="./bin:$PATH"` so this bungler is what happened. If you do that path thinger, don't be surprised if someone seeds your computer with bin directories full of scipts labelled 'ls' and 'cd'.

Oh, and binstubs. Binstubs are fine, they just need a little extra love because I also grow tired of getting back to my project's root any typing `bin/rspec` or `bin/rake all:thethings`. I just want to type `rake` or `rails` or whatever the command is, just like I would with any grown-up bigboy command.

##### Why not just continue typing `bundle exec`?
What, you didn't read the first part? Becuase I'm so damn tired of it. And because of reasons.

It expects all the things.
-------------------------
If you're one of these mercurial weirdos, just fork off... see what I did there? kk.

You need these things:
* **Git** needs to be the vcs for your project.
* **Binstubs**. Generate binstubs for your project. Bungler assumes you're using the `bin` directory off the root of the project. Yes, I understand that it's configuarble via bundler. This is bungler, not bundler. Maybe one day...?
* **Bash**. Because I don't use zsh, or emacs, or insert holy-war-enticing tech here.

I have not tested this at all with OSX. So sorry, I don't have a Mac.

Installation
--------------

1. Check out to ~/

```
$ git clone https://github.com/ahawthorne/bungler.git ~/.bungler
```

2. Add bungler to your `~/.bash_profile`. Ubuntu people, this is `~/.profile`. This ensures it's only source at login rather than every time you open a terminal. I'm looking at you, bashrc.
```
$ echo '[[ -s "$HOME/.bungler/bungle" ]] && . $HOME/.bungler/bungle' >> ~/.bash_profile
```
3. Let bungler know which commands to bungle. This is handled via the `$BUNGLER` environment variable.
```
$ echo 'export BUNGLER="rails rake rspec cucumber"' >> ~/.bash_profile
```
4. Since it would be lame to log out and log back in just to bungle, sorce the file instead.
```
$ . ~/.bungler/bungle
```

#### Upgrading
Just pull in the lateset from the repo
```
$ cd ~/.bungler
$ git pull
```

#### Additionally
If you don't let bungler know that you want it to bungle a command, it's not going to work. Make sure you've added the commands you need to the `$BUNGLER` var.

If you don't have your binstubs set up, bungler will attempt to use a command from your `PATH`.


###License
The MIT License (MIT)

Copyright (c) 2013 Andrew Hawthorne

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

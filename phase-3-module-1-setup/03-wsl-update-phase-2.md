# Update Phase 2 Installations

Now that you have WSL installed, it's time to revisit the software that you may
have installed during Prep Work. Specifically, you need to re-install __Node.js__
through the `nvm` package, and install __Mocha__ to test code.

## nvm and Node.JS

Regardless of whether you completed Prep Work or not, you will need to do a
fresh install of Node.JS through WSL.

Node.JS is Javascript Runtime Environment for running JavaScript files directly
on a computer.  JavaScript is built into every web browser, but if you want
to run JavaScript directly without a browser, you need to install Node.JS.

> NOTE: We do not install Node.JS using the installer provided at the Node.JS
> website from Module 1 onwards this class. If you have this one already
> installed (for example, if you installed it during Prep Work), please
> uninstall it before proceeding with these instructions.

### Node Version Manager (nvm)

Often as a developer, you will need to juggle multiple projects on your computer,
each running a different version of Node.JS. Because of this, just installing a
new version from the Node.JS website would be difficult and error-prone.

Luckily, there's a piece of open source software that can help called Node
Version Manager, or `nvm`.

To install nvm, check out the `nvm` github page here:

[nvm Github Page]

Below the code, there is a README section. Usually when installing software
from github you'll want to check the README for instructions. If you scroll
down you'll see instructions for how to install nvm.  In this case we can run
a special command with `curl` to download and install nvm from the terminal.

So open a Terminal and use the curl command listed in the README.  It should
look something like this, although the version number in the URL might vary:

```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
```

When you do this you'll see something like this:

```shell
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 13527  100 13527    0     0  49731      0 --:--:-- --:--:-- --:--:-- 49915
=> Downloading nvm from git to '/home/your-user/.nvm'
=> Cloning into '/home/your-user/.nvm'...
remote: Enumerating objects: 333, done.
remote: Counting objects: 100% (333/333), done.
remote: Compressing objects: 100% (283/283), done.
remote: Total 333 (delta 38), reused 150 (delta 25), pack-reused 0
Receiving objects: 100% (333/333), 177.16 KiB | 1.46 MiB/s, done.
Resolving deltas: 100% (38/38), done.
=> Compressing and cleaning up git repository

=> Appending nvm source string to /home/your-user/.bashrc
=> Appending bash_completion source string to /home/your-user/.bashrc
=> Close and reopen your terminal to start using nvm or run the following to use it now:

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

The lines to pay attention to are the last three. These are the shell commands
necessary to initialize nvm.  But we don't want to have to run these commands
everytime we open a terminal, so we should put these into our _shell startup file_

The general rule on this is:

If your shell is `zsh`, use `~/.zshrc`
If your shell is `bash`, use `~/.bashrc`

> You can determine which shell you have by typing `echo $SHELL` at the command
> line

You'll notice, in the example above, the nvm installer automatically added the
lines to the `~/.bashrc` even though the example runs zsh.  You need to verify
that the lines were correctly added to your startup file. Don't trust the
installer to always do the right thing in this case. Everyone's system is
different.

To verify it, open up your startup file in vscode with the `code` command. Use
the appropriate startup filename depending on which shell you have (`~/.zshrc`
or `~/.bashrc`).

```shell
code ~/.zshrc
```

If you do not see the nvm startup lines in your file already, add them in there.

There are two ways to run your startup file. You can run it live in your current
shell by typing the `source` command and following it with your startup file, or
an even easier option is to just close your terminal window and open it back up.

Once you have done these steps, run `nvm` by itself at the command prompt. You
should see the help messages from nvm. If this doesn't work, double check your
shell startup files.

### Installing Node.JS

Now that you have nvm installed and ready to go, you can use it to install a
particular version of Node.JS.

Currently in this course, you will use version 18.

> NOTE: Only stick to LTS versions of Node.JS. This stands for Long Term Support.
> These are the stable versions of Node.JS. The odd-numbered releases such as 15
> are experimental releases, and should not be used for anything important. They
> are a way for people to test new releases of Node.JS, not something you should
> rely on for your code.

So let's install it!

```shell
nvm install 18
```

You should see something like this:

```shell
Downloading and installing node v18.17.0...
Downloading https://nodejs.org/dist/v18.17.0/node-v18.17.0-darwin-arm64.tar.xz...
######################################################################### 100.0%
Computing checksum with shasum -a 256
Checksums matched!
Now using node v18.17.0 (npm v8.3.1)
Creating default alias: default -> 18 (-> v18.17.0)
```

You'll notice we can just provide `18` here and not any specific version of
Node.JS like `18.17.0`. nvm is good like that, it will automatically install
the latest version of `18`.

Once this is complete, you should be able to type

```shell
node --version
```

and it should print out the correct version of Node.JS.

You can verify that the Node.JS you installed is coming from your `nvm`
setup, by using this shell command:

```shell
which node
```

If it prints out a path with .nvm in it, then you've done it correctly!

```shell
/home/<<your username>>/.nvm/versions/node/v18.17.0/bin/node
```

Congratulations you've just installed Node.JS!

## Mocha

You will use a tool called Mocha for testing your Javascript code. You will use
it to test in your projects and also when you do assessments. If you already
installed Mocha for Prepwork 2.0, you can skip this step.

To install it, use the `npm` command.

> NOTE: DO NOT confuse `npm` with `nvm`. They are different tools. `nvm`
> controls the version of Node.JS you have installed, while `npm` is responsible
> for installing Node Packages which are third party pieces of software written
> in JavaScript.

To install mocha, do this:

```shell
npm install -g mocha
```

The `-g` is called a flag. This changes the behavior of the install command.

In this case it means `global`.  By default, `npm` will install files into your
project directory.  We want mocha to be installed for all projects, so we
specify `-g`.

You can verify mocha works by typing

`mocha --version`

If it prints out a version number, pat yourself on the back, you have
successfully installed Node.JS and Mocha!

[nvm Github Page]: https://github.com/nvm-sh/nvm

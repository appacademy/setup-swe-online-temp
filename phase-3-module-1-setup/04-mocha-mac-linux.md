# Mocha Setup

You will use a tool called Mocha for testing your Javascript code. You will use
it to test in your projects and also when you do assessments.

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
successfully installed Mocha!

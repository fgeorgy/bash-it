# Bash it

[![Join the chat at https://gitter.im/Bash-it/bash-it](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/Bash-it/bash-it?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

**Bash it** is a collection of community bash commands and scripts. (And a shameless ripoff of [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh). :)

Includes autocompletion, themes, aliases, custom functions, a few stolen pieces from Steve Losh, and more.

Bash it provides a solid framework for using, developing and maintaining shell scripts and custom commands for your daily work. If you're using the _Bourne Again Shell_ (Bash) on a regular basis and have been looking for an easy way on how to keep all of these nice little scripts and aliases under control, then Bash it is for you! Stop polluting your `~/bin` directory and your `.bashrc` file, fork/clone Bash it and start hacking away.

## Install

1. Check a clone of this repo: `git clone --depth=1 https://github.com/Bash-it/bash-it.git ~/.bash_it`
2. Run `~/.bash_it/install.sh` (it automatically backs up your `~/.bash_profile` or `~/.bashrc`, depends on your OS)
3. Edit your modified config (`~/.bash_profile` or `~/.bashrc`) file in order to customize bash it.

**NOTE:**
The install script will also prompt you asking if you use [Jekyll](https://github.com/mojombo/jekyll).
This is to set up the `.jekyllconfig` file, which stores info necessary to use the Jekyll plugin.

**INSTALL OPTIONS:**
The install script can take the following options:

* `--all`: Enable all aliases, plugins and completions.
* `--none`: Don't enable any aliases, plugins or completions.

If none of these parameters is provided, the install script will ask the user.

## Help Screens

```
bash-it show aliases        # shows installed and available aliases
bash-it show completions    # shows installed and available completions
bash-it show plugins        # shows installed and available plugins
bash-it help aliases        # shows help for installed aliases
bash-it help completions    # shows help for installed completions
bash-it help plugins        # shows help for installed plugins
```

## Your Custom scripts, aliases, and functions

For custom scripts, and aliases, just create the following files (they'll be ignored by the git repo):

* `aliases/custom.aliases.bash`
* `completion/custom.completion.bash`
* `lib/custom.bash`
* `plugins/custom.plugins.bash`

Anything in the custom directory will be ignored, with the exception of `custom/example.bash`.

## Themes

There are a few bash it themes.  If you've created your own custom prompts, I'd love it if you shared with everyone else!  Just submit a Pull Request to me (revans).

You can see the theme screenshots  [here](https://github.com/revans/bash-it/wiki/Themes)

Alternatively, you can preview the themes in your own shell using `BASH_PREVIEW=true reload`

## Misc

### Bash Profile Aliases
Bash it creates a 'reload' alias that makes it convenient to reload
your bash profile when you make changes.

### Prompt Version Control Check
Bash it provides prompt themes the ability to check and display version control information for the current directory. The information is retrieved for each directory and can slow down the navigation of projects with a large number of files and folders. Turn version control checking off to prevent slow directory navigation within large projects.

Bash it provides a flag (`SCM_CHECK`) within the `~/.bash_profile` file that turns off/on version control information checking and display within all themes. Version control checking is on by default unless explicitly turned off.

Set `SCM_CHECK` to 'false' to **turn off** version control checks for all themes:

* `export SCM_CHECK=false`

Set `SCM_CHECK` to 'true' (the default value) to **turn on** version control checks for all themes:

* `export SCM_CHECK=true`

**NOTE:**
It is possible for themes to ignore the `SCM_CHECK` flag and query specific version control information directly. For example, themes that use functions like `git_prompt_vars` skip the `SCM_CHECK` flag to retrieve and display git prompt information. If you turned version control checking off and you still see version control information  within your prompt, then functions like `git_prompt_vars` are most likely the reason why.

### Git repository info in the prompt
Bash it can show some information about Git repositories in the shell prompt: the current branch, tag or commit you are at, how many commits the local branch is ahead or behind from the remote branch, and if you have changes stashed.

Additionally, you can view the status of your working copy and get the count of staged, unstaged and untracked files. This feature is controlled through the flag `SCM_GIT_SHOW_DETAILS` as follows:

Set `SCM_GIT_SHOW_DETAILS` to 'true' (the default value) to **show** the working copy details in your prompt:

* `export SCM_GIT_SHOW_DETAILS=true`

Set `SCM_GIT_SHOW_DETAILS` to 'false' to **don't show** it:

* `export SCM_GIT_SHOW_DETAILS=false`

#### pass function renamed to passgen

The Bash it `pass` function has been renamed to `passgen` in order to avoid a naming conflict with the [pass password manager]. In order to minimize the impact on users of the legacy Bash it `pass` function, Bash it will create the alias `pass` that calls the new `passgen` function if the `pass` password manager command is not found on the `PATH` (default behavior).

This behavior can be overridden with the `BASH_IT_LEGACY_PASS` flag as follows:

Set `BASH_IT_LEGACY_PASS` to 'true' to force Bash it to always **create** the `pass` alias to `passgen`:

* `export BASH_IT_LEGACY_PASS=true`

Unset `BASH_IT_LEGACY_PASS` to have Bash it **return to default behavior**:

* `unset BASH_IT_LEGACY_PASS`

## Help out

We think everyone has their own custom scripts accumulated over time.  And so, following in the footsteps of oh-my-zsh, Bash it is a framework for easily customizing your bash shell. Everyone's got a custom toolbox, so let's start making them even better, **as a community!**

Send us a pull request and we'll merge it as long as it looks good. If you change an existing command, please give an explanation why. That will help a lot when we merge your changes in.

Thanks, and happing bashing!


## Contributors

* [List of contributors][contribute]

[contribute]: https://github.com/revans/bash-it/contributors
[pass password manager]: http://www.passwordstore.org/

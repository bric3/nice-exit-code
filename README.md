nice-exit-code plugin for oh-my-zsh
===================================

[oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) plugin that maps exit status code to human readable string.

For example : 

Warning (`1`) : 

```bash
~/.oh-my-zsh-custom/plugins/nice-exit-code ± ❯ git pull origin master:master
From github.com:bric3/nice-exit-code
 ! [rejected]        master     -> master  (non-fast-forward)
↪ WARN ~/.oh-my-zsh-custom/plugins/nice-exit-code ± ❯
```

Command no found (`127`) :

```bash
~/.oh-my-zsh-custom/plugins/nice-exit-code ± ❯ fail
zsh: command not found: fail
↪ CNOTFOUND ~/.oh-my-zsh-custom/plugins/nice-exit-code ± ❯
```

Interrupted (`130`)

```bash
...
* d4eb1c2 - (grin/master) adds grin config (2014-06-21 22:37:14 +0200) Brice Dutheil <brice.dutheil@gmail.com>
* 9447ccb - Adds oh-my-git PR link (2014-06-18 18:07:43 +0200) Brice Dutheil <brice.dutheil@gmail.com>

↪ INT ~ ○ ❯
```


There's no real specifications for status codes, however some are commonly admitted for most programs, the mapping is inspired by [this script](https://github.com/Valodim/zsh-prompt-powerline/blob/master/hooks/prompt-exitnames.zsh)

This function replaces the exit status number with its associated signal name name. Note we can't know for sure if these return codes are actually caused by the signals, but usually they are, since few programs output exit codes superior to `128` for error conditions.
If no matching codes then output the raw code.

To install just add `$(nice_exit_code)` anywhere in your ZSH shell prompt.

```bash
PROMPT='$(nice_exit_code) %n@%m > '
```


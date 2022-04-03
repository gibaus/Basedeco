---
title: ".bashrc"
description: "Learn Linux"
date: 2021-06-13
tags: [Linux]
draft: False
---

Configurer sa console avec .bashrc

Creer des alias

# enable color support of ls and also add handy aliases

if [ "$TERM" != "dumb" ]; then
eval "`dircolors -b`"
alias ls='ls --color=auto'
#alias dir='ls --color=auto --format=vertical'
#alias vdir='ls --color=auto --format=long'
fi

# some more ls aliases

#alias ll='ls -l'
#alias la='ls -A'
#alias l='ls -CF'

alias ls='ls --color=auto'

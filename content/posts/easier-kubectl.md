
---
title: Some Command Line tools I frequently use
author: Sathyajith Bhat
type: post
date: 2022-05-23
url: /2022/05/23/linux-cli
description: 
featured_image: 
meta_image:
categories:
  - DevOps
tags:
  - CLI

---

Some recommended apps, tools to make your CLI life much easier:

### Alternative Shell

macOS now comes with zsh but is poorly configured and doesn't show a lot of context. Adding a shell customization framework like prezto opens up a world of customization options. Even without customizing, prezto gets you a nice prompt thats information like git branch you're on, git status etc. But the more you add to prezto, the slower it can get. For this reason, I would recommend keeping your zprezto rc as light and unchanged as possible. See https://github.com/sorin-ionescu/prezto#installation on how to install. Here's some complementary tools

### A new prompt - starship.rs

An alternative prompt goes a long way in showing context, for example what virtualenv is currently activated, what branch you're on, what Kubernetes context is currently active and more. Starship.rs is a cross-platform, single binary prompt that does this and more, with some great defaults. See https://starship.rs/guide/ on how to install. 

### Smarter cd command

Tired of cd-ing to the same 5 sets of directories over and over again? zoxide is a "smarter" cd command, inspired by z and autojump. zoxide remembers which directories you use most frequently, so you can "jump" to them in just a few keystrokes. Try cd-ing to your favourite repos once or couple of times, then try typing  z sett for it to automagically cd to tropho-runner-settings, saving you a bunch of keystrokes. Give it a try - https://github.com/ajeetdsouza/zoxide



### Fuzzy search for the Terminal

Hunting and pecking for commands with up arrow keys is bad, so we have history search. Now imagine enabling fuzzy-search for your shell history! That's what fzf ("fuzzy finder") does. Shell history is just the start, fzf can fuzzy find almost any list on the command line. See https://github.com/junegunn/fzf#installation on how to install and don't miss the post-install step to enable key bindings.

### Powertools for kubectl

kubectx is a tool to switch between contexts (clusters) on kubectl faster. kubens is a tool to switch between Kubernetes namespaces (and configure them for kubectl) easily. When jumping across the many Kubernetes contexts, these are indispensable. 

### Bonus! 

k9s is a terminal based UI to manage and view all resources of the cluster. Think of it as kube dashboard but for the terminal.
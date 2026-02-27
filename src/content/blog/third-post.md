---
title: 'Tools and Practices That Improved My Developer Workflow'
description: 'A collection of tools, shortcuts, and habits that have made a measurable difference in how I write and ship code.'
pubDate: 'Feb 10 2026'
heroImage: '/assets/blog/blog-placeholder-2.jpg'
---

Over the past few years I've iterated on my development workflow quite a bit. Some changes were small. Others fundamentally changed how I work. Here are the ones that stuck.

## Terminal Multiplexing

I resisted learning tmux for a long time because my IDE's built-in terminal felt "good enough." Then I started working with remote servers and realized I needed persistent sessions that survive disconnects.

Now I use tmux for everything — local development included. Being able to split panes, name sessions, and switch between project contexts without opening new terminal windows has eliminated a surprising amount of friction.

The key bindings take a week or two to internalize, but once they're in muscle memory, you don't think about them anymore.

## Git Aliases and Workflows

I set up a handful of git aliases that I use daily:

```bash
[alias]
  co = checkout
  br = branch
  st = status
  lg = log --oneline --graph --decorate -20
  wip = !git add -A && git commit -m 'wip'
```

The `wip` alias is particularly useful. When I need to switch branches quickly, I commit everything as a work-in-progress and come back to it later. It's faster than stashing, and the reflog keeps everything safe.

I also adopted conventional commits (`feat:`, `fix:`, `chore:`) for all my projects. It seems like overhead at first, but it makes scanning git history much faster and enables automated changelog generation.

## Linting and Formatting on Save

This one sounds obvious, but setting up ESLint and Prettier to run on every file save was a game changer. I stopped thinking about code style entirely. The formatter handles it. I focus on logic.

For new projects, I spend time upfront configuring these tools properly. The investment pays for itself within the first week.

## Keyboard-Driven Navigation

I made a deliberate effort to use the mouse less. This meant learning IDE keyboard shortcuts, using Vim motions in my editor, and navigating my operating system with hotkeys.

The speed difference is real. More importantly, keeping your hands on the keyboard reduces context switching between "thinking" and "navigating." Your flow state is less likely to break.

## Writing Things Down

This isn't a tool, but it's the highest-impact practice on this list. I keep a simple text file where I jot down what I'm working on, what I've tried, and what's blocked. When debugging a tricky issue, this prevents me from going in circles.

At the end of each day, I spend two minutes reviewing what I accomplished. This small habit has made me much better at estimating how long tasks actually take.

## The Common Thread

Every tool and practice here shares one quality: it reduces friction. The best workflow improvements are the ones you stop noticing because they've become automatic. Start with one change, let it settle, then add the next.

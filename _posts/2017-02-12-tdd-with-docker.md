---
layout: post
title: Neovim, TDD and Docker
tags: [neovim, vim, docker, tdd, ruby, rspec]
---

If you, like me, have shortcuts and muscle memory built in neovim (or vim) to
run tests while you develop, you might get frustrated when you change from a
local development environment to a local dockerized development environment.

I use the plugin [vim-test](https://github.com/janko-m/vim-test) with
**Neoterm** and four shortcuts in neovim to run the tests which DO NOT work when
you are working on a dockerized rails application. 

After banging my head on the keyboard because I had to run **rspec** manually,
it came to my mind: *"I can bloody setup an alias in the shell and I can just go
back to my super productive flow! - idiot"*. I ran the following in neoterm:

```sh
alias rspec='docker exec -it <container> rspec'
```

and changed the executable in then neovim configuration for vim-test (by default it
uses `bundle exec rspec`)

```vim
let test#ruby#rspec#executable = 'rspec'
```

and that's it, the speed was back!

Happy TDDing.

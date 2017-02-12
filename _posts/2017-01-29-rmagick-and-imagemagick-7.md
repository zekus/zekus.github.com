---
layout: post
title: rmagick and imagemagick 7
category: ruby, rails
tags: ruby, rails, rmagick, imagemagick
---

The new imagemagick 7 is not compatible (yet) to rmagick (2.16 in my case) so you might have errors like

```shell
Gem::Ext::BuildError: ERROR: Failed to build gem native extension.

    /Users/zekus/.rubies/ruby-2.1.2/bin/ruby extconf.rb
checking for /usr/bin/gcc... yes
checking for Magick-config... no
checking for pkg-config... yes
Package MagickCore was not found in the pkg-config search path.
Perhaps you should add the directory containing `MagickCore.pc'
to the PKG_CONFIG_PATH environment variable
No package 'MagickCore' found
checking for outdated ImageMagick version (<= 6.4.9)... *** extconf.rb failed ***
Could not create Makefile due to some reason, probably lack of necessary
libraries and/or headers.  Check the mkmf.log file for more details.  You may
need configuration options.

Provided configuration options:
	--with-opt-dir
	--with-opt-include
	--without-opt-include=${opt-dir}/include
	--with-opt-lib
	--without-opt-lib=${opt-dir}/lib
	--with-make-prog
	--without-make-prog
	--srcdir=.
	--curdir
	--ruby=/Users/zekus/.rubies/ruby-2.1.2/bin/ruby

extconf failed, exit code 1

Gem files will remain installed in /Users/zekus/.gem/ruby/2.1.2/gems/rmagick-2.16.0 for inspection.
Results logged to /Users/zekus/.gem/ruby/2.1.2/extensions/x86_64-darwin-14/2.1.0-static/rmagick-2.16.0/gem_make.out
```

If you have such an error, your only option at the moment, is to rollback imagemagick to version 6:

```shell
brew uninstall imagemagick
brew install imagemagick@6
brew link imagemagick@6 --force
bundle
```

That should fix it.

Happy coding!

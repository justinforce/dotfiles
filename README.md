dotfiles
========

These are my personal configuration files. The directory structure is designed
so that you can symlink everything with a single command. This is only tested
with and only expected to work on Ubuntu.

Installation
------------

### Copypasta Installation ###

> [Here be dragons!][] This is for **me** to use. The goal is for me to be able
> to copy and paste a couple of lines to get up and running with my local
> configuration. I **definitely want** all of the **potentially destructive**
> actions taken by this script to take place. I'm **not responsible** if you
> lose data or break something using my script. If you **really** want to do all
> of the things that this script does, proceed **at your own peril!**

* Install a couple of prerequisites with APT.
* Clone the repository.
* Run the `rake install` task, symlinking all config files and overwriting any
  existing files.

If you understand the risks and want to press on, copy and paste this (you can
skip the first 2 lines if you have the packages from the 2nd line):

```sh
(
  sudo apt-get update
  sudo apt-get install --yes curl
  curl -L http://b.fiz.bz | bash
)
```

### Manual Installation ###

This method won't overwrite any files and skips some cool magic stuff. This'll
just get you the content, and it's up to you to symlink what you like.

```sh
git clone https://github.com/justinforce/dotfiles ~/.dotfiles --recursive
```

Then you can `cd` into `~/.dotfiles` and run `rake --tasks` to get a list of the
available tasks.

Highlights
----------

I use [vim-plug][] to manage plugins. I use Olivier Verdier's [zsh-git-prompt][]
to get nice git info in my prompt.

Dockerfile?
-----------

Yeah! That's in there so I can quickly check if the bootstrap experience works
end to end on Ubuntu. You can try it. Just do

```sh
docker build .
# ...lots of text...
Successfully built e517a0342623
docker run -it e517a0342623
```

License and Copyright
---------------------

Copyright Justin Force and Licensed under the [MIT license][].

[Here be dragons!]: http://en.wikipedia.org/wiki/Here_be_dragons
[MIT license]: http://www.opensource.org/licenses/MIT
[vim-plug]: https://github.com/junegunn/vim-plug
[zsh-git-prompt]: https://github.com/olivierverdier/zsh-git-prompt

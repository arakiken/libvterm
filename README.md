libvterm with sixel support
===========================

## What's this?

This package provides libvterm which supports DEC Sixel Graphics(*1).
This feature is enabled with the use of DRCS SIXEL extension(*2) which
RLogin 2.23.1 or later and mlterm 3.8.5 or later support.

(*1) https://vt100.net/docs/vt3xx-gp/chapter14.html
(*2) https://raw.github.com/arakiken/mlterm/master/drcssixel/DRCS-SIXEL-v2
    (DRCS SIXEL extension is a fantastic idea which RLogin originally supports.)

## Install

### Build from source package

$ make
$ sudo make install
$ sudo ln -sf $PREFIX/lib/libvterm.so.0 [where official libvterm is installed]/libvterm.so.0
$ nvim
  => Type ":terminal" and enjoy Sixel Graphics in neovim terminal.

## Notice

Applications using libvterm and the terminal emulator where they work should
regard the column width of 0x100000-0x10ffff
(Unicode PUA, Ambiguous width characters) as 1.

For example, "set ambiwidth=single" or apply neovim-0.2.2-drcssixel.patch on
neovim.

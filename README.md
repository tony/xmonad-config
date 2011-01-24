#Tony Narlock's Xmonad, Xmobar, rxvt-uncode configuration
(skiquel @ gmail)

This configuration is used in Xmonad .9 on ubuntu

Getting started
---------------
  On karmic:

    sudo apt-get install rxvt-unicode xmobar xmonad xmonad-contrib

  Open .xinitrc and add:
    exec ck-launch-session xmonad
    xsetroot -solid midnightblue

  Save, Then:

  1.  Move Xdefaults to ~ (cp xmonad-config/Xdefaults ~/.Xdefaults) This is for rxvt-unicode
      (Yes, the X is capital in .Xdefaults!)
  2.  Move xmobarrc to ~ (cp xmonad-config/xmobarrc ~/.xmobarrc) This is for xmobar
  3.  Make .xmonad folder (mkdir ~/.xmonad)
  4.  Move xmonad to ~/.xmonad (cp xmonad-config .xmonad/xmonad.hs)

More kung-fu
------------
  1.  Open your .bashrc and add these 2 alias:

    alias nm-applet='nm-applet -sm-disable &'
    alias trayer='trayer --edge top --align right --SetDockType true --SetPartialStrut true --expand true --width 10 --transparent true --tint 0x000000 --height 12 &'

  2.  :wq
  3.
    source .bashrc   or source .profile
  4.  Now type trayer, then nm-applet via terminal.

Optional
--------
  My favorite coding font is ProggySquareTTSZ, you can grab it from http://www.proggyfonts.com/index.php?menu=download
  To install ProggySquareSZ, extract the ttf into ~/.fonts and do fc-cache -fv

  Then go back into your ~/.vimrc and uncomment the font. The size may have to be changed.

  Oh btw, you may also want to:
  1.  cd /etc/fonts/conf.d
  2.  ln -sf ../conf.avail/10-autohint.conf ./
  3.  ln -sf ../conf.avail/70-yes-bitmaps.conf ./

  Then restart X.

  Also, you may want to change the font size from 12, to 10, to 9, to 8 depending on resolution and dpi.  The files with the fonts are xmonad.hs and .xmobarrc

More tips
---------
  If you're not running Ubuntu, you may not have urxvtcd

  Go into ~/.xmonad/xmonad.hs and change your Terminal from urxvtcd to urxvt.
  Ubuntu has urxvtcd which launches daemon and/or client regardless of whether you already have it running. Other distros will make you run urxvtd first, then urxvtc for every client.

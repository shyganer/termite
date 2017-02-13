TERMITE
=======

## Objective
```
Installer et configurer une instance de termite sur ubuntu.
```

## How to install
### Install necessaries packages
With **shyganer** in **$HOME/b2c/by-other/termite**
```
sudo apt-get install --install-recomends libgtk-3-dev \
										 libpcre2-8-0 \
										 libpcre2-dbg \
										 libpcre2-dev \
										 libvte-2.91-dev
```

### Install VTE-NG library in ubuntu
With **shyganer** in **$HOME/b2c/by-other/termite**
```
sudo apt-get install --install-recommends gtk-doc-tools \
										  valac \
										  libgirepository1.0-dev \
										  libgnutls28-dev \
										  libxml2-utils \
										  gperf
```

### Clone VTE-NG library
With **shyganer** in **$HOME/b2c/by-other/termite**

git clone https://github.com/thestinger/vte-ng.git

### Generate configuration files
With **shyganer** in **$HOME/b2c/by-other/termite**

./autogen.sh
### Install VTE-NG library
With **shyganer** in **$HOME/b2c/by-other/termite**
```
make

sudo make install
```

### Clone Termite repository
With **shyganer** in **$HOME/b2c/by-other/termite**
```
git clone --recursive https://github.com/thestinger/termite.git
```

### Install Termite in ubuntu
With **shyganer** in **$HOME/b2c/by-other/termite**
```
make

sudo make install
```

## How to use
With **shyganer** in **$HOME/b2c/by-other/termite**

termite -v

## Useful commands
```
export PKG_CONFIG_PATH=$(pkg-config --variable pc_path pkg-config)
```

## Errors
### #2
```
Package vte-2.91 was not found in the pkg-config search path.
Perhaps you should add the directory containing `vte-2.91.pc'
to the PKG_CONFIG_PATH environment variable
No package 'vte-2.91' found
Package vte-2.91 was not found in the pkg-config search path.
Perhaps you should add the directory containing `vte-2.91.pc'
to the PKG_CONFIG_PATH environment variable
No package 'vte-2.91' found
g++ -std=c++11 -O3 -Wall -Wextra -pedantic -Winit-self -Wshadow -Wformat=2 -Wmissing-declarations -Wstrict-overflow=5 
-Wcast-align -Wconversion -Wunused-macros -Wwrite-strings -DNDEBUG -D_POSIX_C_SOURCE=200809L 
-DTERMITE_VERSION=\"v12-13-g7738c76\"   -Wno-missing-field-initializers -s -Wl,--as-needed  termite.cc  -o termite
termite.cc:32:21: fatal error: gtk/gtk.h: No such file or directory
compilation terminated.
Makefile:36: recipe for target 'termite' failed
make: *** [termite] Error 1
```
### #3
```
No package 'libpcre2-8' found

Consider adjusting the PKG_CONFIG_PATH environment variable if you
installed software in a non-standard prefix.

Alternatively, you may set the environment variables VTE_CFLAGS
and VTE_LIBS to avoid the need to call pkg-config.
See the pkg-config man page for more details.
```

## Solution
### Fix #1
```
apt-file search gtk+-3.0.pc
libgtk-3-dev: /usr/lib/x86_64-linux-gnu/pkgconfig/gtk+-3.0.pc

sudo apt-get install --install-recommends libgtk-3-dev
```

### Fix #2
```
apt-file search vte-2.91.pc
libvte-2.91-dev: /usr/lib/x86_64-linux-gnu/pkgconfig/vte-2.91.pc

sudo apt-get install --install-recommends libvte-2.91-dev
```

### Fix #3
```
sudo apt-get install --install-recommends libpcre2-8-0
```

## Bugs
```
```

## Todo
```
```

## References
1. https://github.com/thestinger/vte-ng
2. https://github.com/thestinger/termite
1. http://askubuntu.com/questions/210210/pkg-config-path-environment-variable
2. http://epsi-rns.github.io/desktop/2016/09/19/termite-install.html
3. https://github.com/epsi-rns/dotfiles
4. https://wiki.archlinux.org/index.php/Termite

# uim-skk-server-completion
**server completion の機能が本家に実装されたので，このパッチはもはや無意味です．**

[uim](http://code.google.com/p/uim/) の SKK で server completion できるようにするパッチ．
server completion に対応した skkserv は [yaskkserv](http://umiushi.org/~wac/yaskkserv/) 等．

## INSTALL

    % tar xf uim-1.7.0.tar.bz2
    % cd uim-1.7.0
    % patch -Np0 -i ../server-completion.patch
    % ./configure
    % make
    # make install

### for Arch Linux users

    % makepkg -si

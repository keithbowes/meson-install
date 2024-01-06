
When project started to use Meson/Ninja, one thing I really missed was the ability to use [Checkinstall](https://checkinstall.izto.org/).  Well, I finally wrote this script which just uses regular expressions to convert the output of `meson install` or `muon install` into something that checkinstall can understand. So, in autotools-based projects:
```
./configure
make
make install
checkinstall
```

In meson-based projects in which this script is in your path:
```
meson setup build
cd build
ninja
checkinstall meson-install
```

# gfind
This is a graphical frontend for find(1) + grep(1) commands using yad.

## Runtime requirements
```
apt install yad
```

## Build

### For debug purposes you can make links:
```
ln -srfv gfind /usr/local/bin/
ln -srfv share /usr/local/share/gfind/
ln -srfv gfind.desktop /usr/local/share/applications/
```

### For release: deb package
```
mkdir -p gfind_deb/DEBIAN gfind_deb/usr/local/bin gfind_deb/usr/local/share/gfind gfind_deb/usr/local/share/applications

cp deb_control gfind_deb/DEBIAN/control
cp gfind gfind_deb/usr/local/bin/
chmod +x gfind_deb/usr/local/bin/*
cp -r share/* gfind_deb/usr/local/share/gfind/
cp LICENSE gfind_deb/usr/local/share/gfind/
cp README.md gfind_deb/usr/local/share/gfind/
cp gfind.desktop gfind_deb/usr/local/share/applications/

dpkg-deb -Zxz --root-owner-group --build gfind_deb gfind.deb
dpkg-name gfind.deb
```

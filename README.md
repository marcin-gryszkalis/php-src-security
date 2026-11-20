# Manual build on FreeBSD 14

## flags
```
export CFLAGS="-O2 -pipe -fPIC -Wno-error=incompatible-pointer-types -DATTRIBUTE_UNUSED="
export CXXFLAGS="-O2 -pipe -fPIC -Wno-error=incompatible-pointer-types -std=c++17 -DATTRIBUTE_UNUSED="
```

## configure
```
 ./configure --enable-opcache -with-bz2=shared --with-curl=shared --with-gettext=shared --with-iconv=shared --with-imap=shared --with-ldap=shared --with-mysqli=shared --with-openssl=shared --with-pdo_mysql=shared --disable-phar --with-pspell=shared --with-sodium=shared --with-sqlite3=shared --with-xsl=shared --with-zip=shared --with-zlib=shared --with-imap-ssl --enable-bcmath=shared --enable-calendar=shared --enable-ctype=shared --enable-dom=shared --enable-exif=shared --enable-fileinfo=shared --enable-filter=shared --enable-gd=shared --enable-intl=shared --enable-json=shared --enable-mbstring=shared --enable-opcache=shared --enable-pdo=shared --enable-phar=shared --enable-posix=shared --enable-session=shared --enable-simplexml=shared --enable-soap=shared --enable-tokenizer=shared --enable-xml=shared --enable-xmlreader=shared --enable-xmlwriter=shared --without-pdo_sqlite --with-jpeg --with-freetype --with-webp
```

## install
```
rm /php74/usr/local/bin/php-cgi; cat sapi/cgi/php-cgi > /php74/usr/local/bin/php-cgi &&
rm /php74/usr/local/bin/php; cat sapi/cli/php > /php74/usr/local/bin/php &&
chmod +x /php74/usr/local/bin/php* &&
cp modules/*.so /php74/usr/local/lib/php/20190902/
```

---

# Sources

This is a fork of the official PHP repository which receives backport of security fixes from maintained branches.

This branch is **PHP version 7.4.33** with security fixes (see the NEWS file).

# Binary distributions

Known list of providers using this repository as sources for build of old PHP version with extended security support:

## RPM

### Fedora / RHEL / CentOS / AlmaLinux / RockyLinux

* [Remi's RPM repository](https://rpms.remirepo.net/)

## DEB

### Debian / Ubuntu

* [DEB.SURY.ORG](https://deb.sury.org) - Debian [stable](https://wiki.debian.org/DebianStable) and [oldstable](https://wiki.debian.org/DebianOldStable); Ubuntu [LTS](https://ubuntu.com/about/release-cycle)
* [PHP LTS by Freexian](https://www.freexian.com/lts/php/) - Debian [LTS](https://wiki.debian.org/LTS) and [ELTS](https://wiki.debian.org/LTS/Extended) releases; Ubuntu [LTS](https://ubuntu.com/about/release-cycle) and [ESM](https://ubuntu.com/security/esm) releases

## ZIP

### Windows

* [php-eol-security](https://github.com/Jamalofski/php-eol-security) - unofficial builds for Windows x64 and x86, Thread Safe and NTS

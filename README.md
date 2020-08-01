# Azul JDK Debian Package Builder

Azul provides a Debian repository for some arches, but notably not
arm64, and for armhf, they only provide a not-up-to-date version of
JDK8.

Debian's provided `java-package` builder (`make-jpkg`) only supports
Oracle's JVM packages.  After adding support for Azul releases, I
couldn't get it working (and also found that it wasn't working properly
even for Oracle releases on ARM).

So I decided to write something quick-and-dirty.

This requires no dependencies beyond `tar` `gzip`, and `dpkg-deb`
(1.19.0 or higher).

Simply run:

```
./azul-jdk-deb /path/to/zulu/tar/gz
```

If you want a package revision field other than `1`, pass it as the
second argument.

Note that (unlike `make-jpkg`) this can also build packages for
non-native arches.

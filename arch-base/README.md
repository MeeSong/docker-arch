# arch-base

> from [mkimage-arch.sh](https://github.com/docker/docker/blob/master/contrib/mkimage-arch.sh)

meesong/arch-base

Archlinux 2016.11.25 Minimal arch installation

Generated with mkimage-arch.sh

Generated Step:

```bash
$ chmod +x mkimage-arch.sh
$ cp /etc/pacman.conf ./mkimage-arch-pacman.conf # or get a pacman.conf from somewhere else
$ ./mkimage-arch.sh
# docker run -t -i --rm archlinux /bin/bash  # try it
```

For slow network connections or CPU, the build timeout can be extended:

```bash
$ sed -i 's/timeout 60/timeout 120/' mkimage-arch.sh
```

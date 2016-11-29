#meesong/archlinux

FROM meesong/arch-base:latest

MAINTAINER MeeSong <meesong@outlook.com>

# Pacman config
COPY pacman.conf /etc/pacman.conf
COPY mirrorlist /etc/pacman.d/mirrorlist
RUN chmod 644 /etc/pacman.conf /etc/pacman.d/mirrorlist

# Time zone
ENV TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Packages
RUN set -x \
    && pacman -Syu \
    && pacman -S --noconfirm yaourt archlinuxcn-keyring \
    && pacman -S --noconfirm vim wget git openssh zsh \
    && sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

WORKDIR /home
ENTRYPOINT ["/bin/zsh"]

# Distro-Deb-I3WM
Distro Based Debian Stable, i3wm, Developer

## Construindo a Imagem
Requisitos:
* Instalação do Debian Stable;
* Conexão com a internet;
* 15 GB de espaço livre de armazenamento;

Instalar live-build:
```
$ sudo apt install live-build
```
Configurar live-build:
```
$ lb config \
     --bootappend-live "boot=live components locales=pt_BR.UTF-8 keyboard-layouts=br hostname=distro-deb-i3wm username=user00" \
     --debian-installer live \
     --distribution buster \
     --apt-indices false \
     --apt-source-archives false \
     --archive-areas "main contrib non-free" \
     --updates true \
     --backports true \
     --mirror-bootstrap http://deb.debian.org/debian/ \
     --mirror-chroot http://deb.debian.org/debian/ \
     --mirror-chroot-security http://security.debian.org/debian-security/ \
     --mirror-binary http://deb.debian.org/debian/ \
     --mirror-binary-security http://security.debian.org/debian-security
```
Construindo a imagem:
```
$ sudo lb build
```

Atenção: O processo de construção da imagem pode ser bem demorado dependendo da configuração do computador e/ou conexão com à internet.

Dica: Antes de um novo build rode `sudo lb clean --binary`.

## License

GPLv3 or later.

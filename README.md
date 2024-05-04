### 🔥 on Fedora 40

> Depending your system you may need to `sudo`

#### Install system deps

```
dnf install libbsd binutils
```

#### Fetch needed libraries
```
mkdir /opt/mojo-deps/
cd /opt/mojo-deps/
```

```
wget https://ftp.debian.org/debian/pool/main/n/ncurses/libncurses6_6.4-4_amd64.deb
ar -xv libncurses6_6.4-4_amd64.deb
tar -xf data.tar.gz
```

```
wget https://ftp.debian.org/debian/pool/main/n/ncurses/libtinfo6_6.4-4_amd64.deb
ar -xv libtinfo6_6.4-4_amd64.deb
tar -xf data.tar.gz
```

```
wget https://ftp.debian.org/debian/pool/main/libe/libedit/libedit2_3.1-20221030-2_amd64.deb
ar -xv libedit2_3.1-20221030-2_amd64.deb
tar -xf data.tar.gz
```

#### Install Mojo
```
export LD_LIBRARY_PATH=/opt/mojo-deps/lib/x86_64-linux-gnu:/opt/mojo-deps/usr/lib/x86_64-linux-gnu:$LD_LIBRARY_PATH

modular auth

modular install mojo

echo 'export MODULAR_HOME="/home/$USERNAME/.modular"' >> ~/.zshrc                             
echo 'export PATH="/home/$USERNAME/.modular/pkg/packages.modular.com_mojo/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

#### Run the 🔥 REPL with:
```
export LD_LIBRARY_PATH=/opt/mojo-deps/lib/x86_64-linux-gnu:/opt/mojo-deps/usr/lib/x86_64-linux-gnu:$LD_LIBRARY_PATH
mojo
```

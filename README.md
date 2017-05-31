###  Tox Protocol Plugin For Pidgin / libpurple - discontinued

Sorry everyone, but I will not continue this project any further. I am using
one of the available Tox clients with audio and video support and since I
do not need the Pidgin tox plugin myself I won't spend any time on it.

I'll leave this repo around in case someone wants to fork and continue, but I
disabled issues and basically I won't be taking care of this code any more.


### logrusorgru cahnges

+ Moved to github.com/TokTok/toxcore

##### Ubuntu 17.10 installation

```sh
sudo apt-get install libsodium-dev libtoxcore-toktok-dev

git clone https://github.com/logrusorgru/tox-prpl.git
cd tox-prpl

# create temporary directory
mkdir -pv tmp

autoreconf -i
./configure --prefix=./tmp/
make
make install

cp -v ./tmp/lib/purple-2/libtox.so ~/.purple/plugins/

# install pixmaps
sudo cp -rv ./tmp/share/pixmaps/pidgin/protocols/* \
    /usr/share/pixmaps/pidgin/protocols/
```

Run Pidgin and create account. If you already hava an account, created with
other Tox messanger, then you need to replace tox-file
 `.purple/tox/toxedpidgin/tox_save.tox`

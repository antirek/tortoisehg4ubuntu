# tortoisehg4ubuntu
Script to use tortoisehg on ubuntu 20.04 or higher

Ubuntu packages to test are available in the "Releases" section.


# Downloads
[![Github All Releases](https://img.shields.io/github/downloads/glaure/tortoisehg4ubuntu/total)]()

## Inspired by:
https://askubuntu.com/questions/1232173/how-to-install-the-tortoisehg-in-ubuntu20-04


## Instructions

Install all necessary build prerequisites
```
sudo ./bootstrap.sh
```

Build thg (tortoisehg)
```
./build.sh
```


## Manual Instructions
If you have trust issues to run the scrip as root, refer to the manual installation steps:


I do not have a working package or snap. But using these instructions, it is rather easy to get tortoisehg working from source.

Check that python --version returns a Python 3 interpreter. If not, you have to change the symlink /usr/bin/python to /usr/bin/python3.


OK:
```
$ python --version
Python 3.8.2
```

Not OK:
```
$ python --version
Python 2.7.18rc1
```

Change the symlink:
```
$ sudo rm /usr/bin/python
$ sudo ln -s /usr/bin/python3 /usr/bin/python
```

pip3 is needed to fulfill all the build dependencies.
```
sudo apt install python3-pip build-essential
```

Change into thg directory.
```
cd thg
```

Install PyQt5.
```
pip3 install pyqt5
```

Install mercurial.
```
pip3 install mercurial==5.4
```

Install Qscintilla.
```
pip3 install qscintilla
sudo apt install pyqt5.qsci-dev
sudo apt install python3-pyqt5.qsci
```

Clone tortoisehg repository.
```
hg clone https://foss.heptapod.net/mercurial/tortoisehg/thg
hg revert -r 5.4.2 --all

```

Lets build tortoisehg for inplace usage.
```
make local
```

Start tortoisehg.
```
./thg
```

I got tortoisehg working on multiple different Ubuntu 20.04 installations using this recipe.


------------------------

Also can help install or reinstall xinerama

```
sudo apt install libxcb-xinerama0

sudo apt-get install --reinstall libxcb-xinerama0
```




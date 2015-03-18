# `motd.dynamic`
`motd` script for `linux` written in `python`, highly configurable and lots of eyecandy

## Installation

1. Assuming you have `apt-get` (`debian` based dists), you need to:

```shell
sudo apt-get update
sudo apt-get install python python-dev pip fortune fortunes cowsay
sudo pip install -U pyfiglet uptime ipgetter psutil futures git+http://github.com/bufordtaylor/python-texttable
```
Or do this if you have [`apt-fast`](https://github.com/ilikenwf/apt-fast):

```shell
sudo apt-fast update
sudo apt-fast install python python-dev pip
sudo apt-fast install fortune fortunes cowsay
sudo pip install -U pyfiglet uptime ipgetter psutil futures git+http://github.com/bufordtaylor/python-texttable
```

TODO!

### Deciding on a figlet font:

Can't decide what figlet font to use? Run this in and replace `<text>` with the text you wish to use.

```shell
pyfiglet -l | while read line ; do echo $line && echo && pyfiglet <text> --font=$line ; done > figletfonts
```

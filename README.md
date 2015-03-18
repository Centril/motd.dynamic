# `motd.dynamic`
> `motd` script for `linux` written in `python`, highly configurable with lots of eyecandy.
> It runs all the information gathering in separate concurrent proccesses and thus fast, relatively speaking.

## Features

`motd.dynamic` reports the following information:

1. Uptime.
2. Booted on.
3. System time.
4. System info (dist, os, release-version, arch).
5. Usage of `/`, same as running `df /` - with color warnings if not enough free space.
6. sshd sessions reporting: all the logged-in users and how many per user. Color notification if root is on.
7. Memory usage & Swap usage.
8. Load average.
9. Number of processes (total and for current user).
10. Public hostname & IP.
11. Internal hostname & IP.
12. Apt upgrades reporting.

Additionally, it provides a nice colorized banner made with `figlet` as well as something like the following, but more elegantly and with colors:
```shell
fortune | cowsay
```

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

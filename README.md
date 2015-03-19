[![Gittip]][url: Gittip] [![License]][url: License] [![Semver]][url: Semver]

# [`motd.dynamic`]
> `motd` script for `linux` written in `python`, highly configurable with lots of eyecandy.
> It runs all the information gathering in separate concurrent proccesses and thus is fast, relatively speaking.

## Features

[`motd.dynamic`] reports the following information:

+ [`uptime`].
+ [`booted on`][`uptime`].
+ `system time`.
+ `system info` (dist, os, release-version, arch).
+ usage of `/`, same as running [`df /`] - with color warnings if not enough free space.
+ `sshd sessions` reporting: all the logged-in users and how many per user. Color notification if root is on.
+ `memory usage & swap usage`.
+ [`load average`].
+ `number of processes` (total and for current user).
+ `public hostname & IP`.
+ `internal hostname & IP`.
+ [`apt-get upgrades reporting`].

Additionally, it provides a nice colorized banner made with [`figlet`], or [`pyfiglet`] to be precise, as well as something like the following, but more elegantly and with colors, using [`fortune`] and [`cowsay`]:

```shell
fortune | cowsay
```

## Installation

##### 1 - Prerequisites

Assuming you have [`apt-get`] - installed on `debian` based dists, you need to:

```shell
sudo apt-get update
sudo apt-get install python python-dev pip fortune fortunes cowsay
sudo pip install -U pyfiglet uptime ipgetter psutil futures git+http://github.com/bufordtaylor/python-texttable
```

Or do this if you have [`apt-fast`]

```shell
sudo apt-fast update
sudo apt-fast install python python-dev pip
sudo apt-fast install fortune fortunes cowsay
sudo pip install -U pyfiglet uptime ipgetter psutil futures git+http://github.com/bufordtaylor/python-texttable
```

##### 2 - Clone the repo:

```shell
cd /opt
git clone https://github.com/Centril/motd.dynamic/
cd motd.dynamic
chmod +x motd.dynamic
```

##### 3 - Configure & Edit [`motd.dynamic`] with your favourite editor.
```shell
nano motd.dynamic
```

##### 4 - Add script to `/etc/profile`.

```shell
 echo /opt/motd.dynamic/motd.dynamic | sudo tee -a /etc/profile
```

## Deciding on a figlet font:

Can't decide what figlet font to use? Run this in and replace `<text>` with the text you wish to use.

```shell
pyfiglet -l | while read line ; do echo $line && echo && pyfiglet <text> --font=$line ; done > figletfonts
```

<!-- references -->

[Gittip]: http://img.shields.io/gittip/lefoy.svg?style=flat
[url: Gittip]: https://www.gittip.com/lefoy/
[License]: http://img.shields.io/badge/license-GPL2.0-blue.svg?style=flat
[url: License]: https://github.com/lefoy/cyanide-theme/blob/master/LICENSE.md
[Semver]: http://img.shields.io/badge/semver-2.0.0-blue.svg?style=flat
[url: Semver]: http://semver.org/spec/v2.0.0.html

[`motd.dynamic`]: https://github.com/Centril/motd.dynamic/

[`uptime`]: https://github.com/Cairnarvon/uptime
[`load average`]: http://blog.scoutapp.com/articles/2009/07/31/understanding-load-averages
[`apt-get upgrades reporting`]: https://nickcharlton.net/posts/debian-ubuntu-dynamic-motd.html
[`df /`]: http://en.wikipedia.org/wiki/Df_%28Unix%29
[`apt-get`]: http://linux.die.net/man/8/apt-get
[`apt-fast`]: https://github.com/ilikenwf/apt-fast
[`pyfiglet`]: https://github.com/pwaller/pyfiglet
[`figlet`]: http://www.figlet.org/
[`cowsay`]: http://en.wikipedia.org/wiki/Cowsay
[`fortune`]: http://en.wikipedia.org/wiki/Fortune_%28Unix%29

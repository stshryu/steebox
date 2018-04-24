# steebox information
## Included components
*  Python 3.5.x
  *  pip
  *  discord.py (Rapptz)
  *  BeautifulSoup (bs4)
  *  virtualenv
*  Sqlite3 (CLI)
*  ansible
*  steebot Git Repo [Branch: MASTER]
*  cowsay

## Installation

1. Install VirtualBox
2. Install Vagrant
3. Run command `vagrant init stshryu/steebox --box-version 1.0.0`
4. vagrant up 
5. vagrant ssh
6. Steebot dev environment should now be up and running.

## Instructions

Use `git status` while in `~/github/steebot` to ensure that you are working with the most recent steebot 
repository

### Configuration
1. Add a folder named config under `~/github/steebot/config/`. 
2. In `config/` add a file called `config.ini`
3. Edit `config.ini` and add these following config keys

```
[Bot Info]
['username'] = '...'
['token'] = '...'
['ownerID'] = '...'

[App Info]
['secret'] = '...'
['ID'] = '...'

[Twitch Info]
['ID'] = '...'
['secret'] = '...'
```

4. Add a folder named `database` to `~/github/steebot/`
5. Initialize a SQLITE3 database called `servers.db` in `database`
6. steebot should be good to go

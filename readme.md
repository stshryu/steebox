# steebox information
## Included components
*  Python 3.5
*  pip
*  discord.py (Rapptz)
*  BeautifulSoup (bs4)
*  virtualenv
*  Sqlite3 (CLI)
*  ansible
*  cowsay

## Installation

1. Install VirtualBox
2. Install Vagrant
3. copy the contents of Vagrantfile into your own Vagrantfile
4. vagrant up 
5. vagrant ssh
6. Steebot dev environment should now be up and running

## Instructions


Your folder that contains `Vagrantfile` in the host machine will automatically be mounted as a shared folder in the linux guest, so remember to clone your working steebot repository into that folder in order to access everything from within the machine.

You may need to add the following lines below into your Vagrantfile on Windows hosts if you get an error.

```
config.vm.provider "virtualbox" do |v|
  v.customize [ "modifyvm", :id, "--uartmode1", "disconnected" ]
end
```

Additionally, if you wish to have your shared folder in the home screen when you ssh into vagrant, add this line into your Vagrantfile:

```
config.vm.synced_folder "../<folder_name>", "/home/vagrant/vagrant"
```

Where `<folder_name>` is replaced with the folder that contains Steebot. If the Vagrantfile is in the folder Steebot is in, all you need to type is `"."` for the folder name.

### Configuration
1. Add a folder named config under `steebot/config/`. 
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

4. Add a folder named `database` to `steebot/`
5. Initialize a SQLITE3 database called `servers.db` in `database`
6. steebot should be good to go

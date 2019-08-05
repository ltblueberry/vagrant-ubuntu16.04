# Vagrant for Ubuntu 16.04
Ubuntu 16.04 Vagrantfile

# MacOS Install Vagrant
Install Vagrant via `brew`
```
brew cask install virtualbox
brew cask install vagrant
brew cask install vagrant-manager
```

# SSH-key
Generate separate ssh-key special for vagrant
```
ssh-keygen
```
save key to  **~/.ssh/localvagrant_rsa**

# SSH-config

Append ssh host config to **~/.ssh/config**
```
Host vagrant 192.168.100.100
    HostName 192.168.100.100
    IdentityFile ~/.ssh/localvagrant_rsa
    User root
```

# Local network
Vagrant machine will be available at **192.168.100.100**.

# How to up, stop, remove vagrant machine
In folder with **Vagrantfile** execute next commands:

To launch vagrant machine
```
vagrant up
```

To stop vagrant machine
```
vagrant halt
```

To remove vagrant machine
```
vagrant destroy
```

# Connect to vagrant machine via SSH

Execute command
```
ssh vagrant
```

# Some problems with SSH

You can have next error after removing vagrant machine
```
WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!

Add correct host key in ~/.ssh/known_hosts to get rid of this message.
ECDSA host key for 192.168.100.100 has changed and you have requested strict checking.
Host key verification failed.
```

Just remove fingeprint for ip address 192.168.100.100 from **~/.ssh/known_hosts**

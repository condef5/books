# List of programs for install in linux

### Instalar fish

```sh
sudo apt-get update
sudo apt-get install fish

```
### Instalar oh my fish

```sh
sudo apt-get update
curl -L https://github.com/oh-my-fish/oh-my-fish/raw/master/bin/install > install
fish install
```
Note: set fish as default shell `chsh -s /usr/bin/fish `


### Icons 

```sh
$ sudo apt-get update
$ sudo apt-get install macbuntu-os-icons-lts-v7
$ sudo apt-get install macbuntu-os-ithemes-lts-v7
```

### Node

```sh
$ sudo apt-get install curl python-software-properties
curl -sL https://deb.nodesource.com/setup_7.x | sudo bash -

$ sudo apt-get install nodejs

```

### Yarn

```sh
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

$ sudo apt-get update && sudo apt-get install yarn

```

### Create-react-app

```sh

yarn global add create-react-app

```
### Postgresql

```sh

$ sudo apt-get update
$ sudo apt-get install postgresql postgresql-contrib

```
note: más información [aquí](https://www.digitalocean.com/community/tutorials/como-instalar-y-utilizar-postgresql-en-ubuntu-16-04-es) 

### Simple screen recorder

```sh
sudo add-apt-repository ppa:maarten-baert/simplescreenrecorder
$ sudo apt-get update
$ sudo apt-get install simplescreenrecorder
```

### Theme MacUbuntu

```sh
sudo add-apt-repository ppa:noobslab/macbuntu
$ sudo apt-get update
$ sudo apt-get install macbuntu-os-icons-lts-v7
$ sudo apt-get install macbuntu-os-ithemes-lts-v7
$ sudo apt-get install macbuntu-os-lightdm-lts-v7
```

### Instalar docky

```sh
sudo add-apt-repository ppa:docky-core/ppa
$ sudo apt-get update
$ sudo apt-get install docky

```


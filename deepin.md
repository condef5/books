# Initial setup in [deepin](https://www.deepin.org/es/download/)

Install git:
```
sudo apt install git
```

Install curl:
```
sudo apt install curl
```

Install font super cool
```
sudo apt-get install fonts-firacode
```

Install brewlinux:
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/Linuxbrew/install/master/install.sh)"
sudo apt-get install build-essential
```

Add to path:
```
echo "eval $(/home/linuxbrew/.linuxbrew/bin/brew shellenv)" >> ~/.bashrc
```

Install chruby
```
brew install chruby
echo "source /home/linuxbrew/.linuxbrew/opt/chruby/share/chruby/chruby.sh" >>~/.bashrc
echo "source /home/linuxbrew/.linuxbrew/opt/chruby/share/chruby/auto.sh" >>~/.bashrc
```

Install ruby-install
```
brew install ruby-install
ruby-install ruby
echo "ruby-2.6.3" > ~/.ruby-version
```

```
sudo apt-get install postgresql postgresql-contrib libpq-dev
sudo -u postgres createuser -s $(whoami); createdb $(whoami)
sudo -i -u postgres
psql
ALTER ROLE username WITH SUPERUSER;
```

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0 install.sh | bash
nvm ls-remote
nvm install 12.8.0
```

```
sudo apt-get install sqlite3 libsqlite3-dev
```

Set default shells
```
chsh -s /usr/bin/fish
```

List shells: `cat /etc/shells`

`omf install linuxbrew`

`home/condef5/.local/share/omf/pkg/linuxbrew`

setup fish ruby
```
wget -O chruby-fish-0.8.2.tar.gz https://github.com/JeanMertz/chruby-fish/archive/v0.8.2.tar.gz
tar -xzvf chruby-fish-0.8.2.tar.gz
cd chruby-fish-0.8.2/
sudo make install
```

edit `nano ~/.config/fish/config.fish` and paste
```
set CHRUBY_ROOT '/home/linuxbrew/.linuxbrew/opt/chruby'
source /usr/local/share/chruby/chruby.fish
source /usr/local/share/chruby/auto.fish
```

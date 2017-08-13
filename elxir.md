Add Erlang Solutions repo: 

```sh
wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb && sudo dpkg -i erlang-solutions_1.0_all.deb
```

Modificar el archivo que apunta al origen donde están ubicados los binarios del lenguaje.

```sh
sudo nano /etc/apt/sources.list.d/erlang-solutions.list
```
Cambiar la palabra squeeze por wheezy `ctrl + x` y aceptamos con la tecla `y` 

Run:

```sh 
sudo apt-get update
```

Install the Erlang/OTP platform and all of its applications: 

```sh
sudo apt-get install esl-erlang
```

Install Elixir: 

```sh
sudo apt-get install elixir
```
## Update Elixir 

```sh
  git clone https://github.com/elixir-lang/elixir.git
  cd elixir/
  git checkout v1.4
  make clean test
  sudo make install
```

## Install Phoenix Framework

```sh
  mix archive.install https://github.com/phoenixframework/archives/raw/master/phoenix_new.ez
```
Crear un proyecto

```sh
$ cd <my_new_app_name>
$ mix ecto.create                     
$ mix phoenix.server   
```
note: Is necesary install Inofity-tools: `sudo apt-get install inotify-tools`



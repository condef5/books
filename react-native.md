# Steps for ReactNative

Pasos para instalar react-native en linux

## Instalar java 8 SDK

Instalar con los sgts comandos

```sh
sudo apt-get install python-software-properties
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
```

## Instalar nodejs

```sh
$ sudo apt-get install curl python-software-properties 
$ curl -sL https://deb.nodesource.com/setup_7.x | sudo bash -
$ sudo apt-get install nodejs
```

## Instalar react-native-cli

```sh
$ sudo npm install -g react-native-cli
```


## Instalar android studio

Descargar el instalador [aquí](https://developer.android.com/studio/index.html)
Extraer la carpeta android-studio y moverla al directorio opt

```sh
$ sudo mv androi-studio /opt/
```

Agregar esto al path

```sh
$ nano ~/bashrc
```

```sh
export ANDROID_HOME=$HOME/Android/Sdk
export PATH=$PATH:$ANDROID_HOME/tools
```

### Notes

For more info visit this [link](https://www.youtube.com/watch?v=y7aPKTOnUUQ&list=PL2g-DF7-WOZ4pzupMZfBJiDEh_OLRvBRy&index=4)


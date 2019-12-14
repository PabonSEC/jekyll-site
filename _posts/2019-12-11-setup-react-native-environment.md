---
layout: post
title:  "Setup react-native environment on Ubuntu for Android"
date:   2019-12-11 23:45:27 +0600
featured-image: 'react-native.png'
categories: React-Native
tags: [react-native]
---

<h3><i class="fab fa-node"></i> Install node and npm</h3>

**Using Ubuntu**

```bash
$ sudo apt install curl
$ curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
$ sudo apt-get install -y nodejs
$ node -v
v10.17.0
$ npm -v
6.11.3
```

**Using Debian, as root**

```bash
$ curl -sL https://deb.nodesource.com/setup_10.x | bash -
$ sudo apt-get install -y nodejs
```

<br/>
<h3><i class="fas fa-angle-right"></i> Install react-native-cli</h3>

```bash
$ sudo npm install -g react-native-cli
$ react-native --version
react-native-cli: 2.0.1
```

<br/>
<h3><i class="fab fa-android"></i> Setup Android development environment</h3>

**[Download android studio](https://developer.android.com/studio/index.html)**. In my case downloaded file's name was `android-studio-ide-191.6010548-linux.tar.gz` and I kept it into my home directory. Then follow these steps

```bash
$ cd ~
$ tar xvzf android-studio-ide-191.6010548-linux.tar.gz
$ cd android-studio/bin/
$ ./studio.sh
```

After completing the installation of android studio, you need to install these from android studio.

- **Android SDK**
- **Android SDK Platform**
- **Android Virtual Device**

To do that just go to `Appearance & Behavior → System Settings → Android SDK` from android studio and select your SDK platform and install.

Then you need to set up `ANDROID_HOME` environment variables in order to build react native apps with native code. Now edit your `.bashrc` file and add these lines into it.

```bash
export ANDROID_HOME=$HOME/Android/Sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

After adding those lines save it and run `source .bashrc` via terminal to keep running source to get the aliases working in any new login terminal instances.

```bash
$ source .bashrc
```

<br/>
<h3><i class="fab fa-java"></i> Install java on your Ubuntu system</h3>

```bash
$ sudo apt update
$ sudo apt install default-jdk
$ java -version
# Output
openjdk version "11.0.4" 2019-07-16
OpenJDK Runtime Environment (build 11.0.4+11-post-Ubuntu-1ubuntu218.04.3)
OpenJDK 64-Bit Server VM (build 11.0.4+11-post-Ubuntu-1ubuntu218.04.3, mixed mode, sharing)
```

So you have successfully installed `java` on your `Ubuntu` system. My version was `Ubuntu 18.04.3 LTS`. At this point you are all set of working with react-native.

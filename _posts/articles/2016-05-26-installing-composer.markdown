---
layout: post
category: article
title:  "Installing composer on Ubuntu 14.04"
date: 2016-05-26 23:09:25 +0530
image: 2016/05/26/composer.png
meta: This article explains about installing composer on Ubuntu 14.04
permalink: /article/installing-composer-on-ubuntu
author: Ritesh Shrivastav
---
Composer is a dependency manager for PHP. It manage the dependencies you require on a project by project basis. This means that Composer will pull in all the required libraries, dependencies and manage them all in one place. In this article we'll install Composer on Ubuntu 14.04 server.

### 1. Installing the Dependencies
Before we download and install Composer, we need to make sure our server has all dependencies installed.

First, update the package manager cache by running:

```
sudo apt-get update
```

Now, let's install the dependencies. We'll need ``curl`` in order to download Composer and php5-cli for installing and running it. git is used by Composer for downloading project dependencies. Everything can be installed with the following command:

```
sudo apt-get install curl php5-cli git
```

### 2. Downloading and Installing Composer
Composer installation is really simple and can be done with a single command:

```
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
```

This will download and install Composer as a system-wide command named ``composer``, under ``/usr/local/bin``. The output should look like this:

```
Output
#!/usr/bin/env php
All settings correct for using Composer
Downloading...

Composer successfully installed to: /usr/local/bin/composer
Use it: php /usr/local/bin/composer
To test your installation, run:

composer
```

And you should get output similar to this:

```
Output
   ______
  / ____/___  ____ ___  ____  ____  ________  _____
 / /   / __ \/ __ `__ \/ __ \/ __ \/ ___/ _ \/ ___/
/ /___/ /_/ / / / / / / /_/ / /_/ (__  )  __/ /
\____/\____/_/ /_/ /_/ .___/\____/____/\___/_/
                    /_/
Composer version 1.0-dev (9859859f1082d94e546aa75746867df127aa0d9e) 2015-08-17 14:57:00

Usage:
 command [options] [arguments]

Options:
 --help (-h)           Display this help message
 --quiet (-q)          Do not output any message
 --verbose (-v|vv|vvv) Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug
 --version (-V)        Display this application version
 --ansi                Force ANSI output
 --no-ansi             Disable ANSI output
 --no-interaction (-n) Do not ask any interactive question
 --profile             Display timing and memory usage information
 --working-dir (-d)    If specified, use the given directory as working directory.

. . .
```

This means Composer is succesfully installed on your system.
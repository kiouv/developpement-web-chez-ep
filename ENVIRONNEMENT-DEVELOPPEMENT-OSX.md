# Environnement de développement sur OSX

*Pour Linux et Windows, écriture en cours...*

## Sommaire

* [Introduction](#markdown-header-introduction)
    * [Public ciblé](#markdown-header-public-vise)
    * [Configuration minimum](#markdown-header-configuration-minimum)
* [Lancer Sublime depuis le terminal](#markdown-header-lancer-sublime-depuis-le-terminal)

## Introduction

Ce guide doit vous permettre d'installer un environnement de développement complet sur votre machine OSX.

Cet environnement vous permettra de :

1. initialiser rapidement un site statique ou avec PHP / MySQL
2. développer efficacement en local
3. déployer simplement sur un serveur externe

Prévoyez 2 bonnes heures pour mettre tout ça en place.

### Public ciblé

Ce document est destiné au développeur avec un minimum d'expérience. En effet, il nécessite de maitriser les domaines suivants :

* GIT
* Grunt
* La manipulation de fichiers en ligne de commande via le terminal
* node.js, Jade, Stylus, PHP...

### Configuration minimum

OSX, [Sublime Text](http://www.sublimetext.com/), et le reste nous verront ensemble.

## Lancer Sublime depuis le terminal OSX

vim ou nano, c'est sympa, mais SUblime Text, c'est mieux. Voici quelques instructions pour ouvrir un fichier ou un dossier avec Sublime text depuis le terminal.

Ouvrez le terminal. Vérifiez que Sublime est bien installé là où il doit être

#### Pour Sublime Text 2

    open /Applications/Sublime\ Text\ 2.app/Contents/SharedSupport/bin/subl

#### Pour Sublime Text 3

    open /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl

Si Sublime se lance, on est bien.

On va maintenant créer un symlink appelé `subl` pour lancer sublime depuis le terminal

#### Pour Sublime Text 2

    ln -s /Applications/Sublime\ Text\ 2.app/Contents/SharedSupport/bin/subl /usr/local/bin/subl

#### Pour Sublime Text 3

    ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl

La dernière chose à faire est de vérifier si votre profil système regarde bien au bon endroit pour voir le symlink que l'on vient de créer.

    open ~/.bash_profile

Dans ce fichier, vous devez trouver la ligne qui commence par `export PATH=`. Votre `PATH` contient tous les répertoires qui vont être observés dès lors que vous entrez une commande dans le terminal. Normalement, vous verrez ça :

    export PATH=/usr/local/bin:(...)

Si ce n'est pas le cas, ajoutez simplement `/usr/local/bin` à votre `PATH` et sauvegardez le fichier.

Note : les (...) dans l'exemple représentent les autres dossiers déja présents dans votre `PATH`.

Si vous n'avez pas de `PATH` dans votre fichier, ajoutez simplement cette ligne

    export PATH=/usr/local/bin:$PATH

Sauvegardez et fermez le fichier, puis rechargez votre profil avec 

    source ~/.bash_profile

Vérifions si ça marche ! avec `cd`, baladez vous dans un dossier, puis essayez les commandes suivantes :

    subl . # ouvre tous les fichiers et dossiers

    subl filename # ouvre un fichier

    subl foldername # ouvre un dossier

Et voilà !

*Source : http://ashleynolan.co.uk/blog/launching-sublime-from-the-terminal*




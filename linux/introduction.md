# Introduction LINUX

<!--toc:start-->
- [Introduction LINUX](#introduction-linux)
  - [Distributions](#distributions)
  - [Système d'exploitation UNIX](#système-dexploitation-unix)
    - [Caractéristiques du système UNIX](#caractéristiques-du-système-unix)
  - [Connexion et déconnexion](#connexion-et-déconnexion)
  - [Introduction à la notion de système de fichiers (file system)](#introduction-à-la-notion-de-système-de-fichiers-file-system)
    - [Notion de fichier et de répertoire](#notion-de-fichier-et-de-répertoire)
    - [Nomenclature des fichiers](#nomenclature-des-fichiers)
    - [Les différents types de fichiers](#les-différents-types-de-fichiers)
    - [Système de fichiers](#système-de-fichiers)
      - [Quelques principaux répertoires Unix](#quelques-principaux-répertoires-unix)
      - [Les répertoires *point* et *point point*](#les-répertoires-point-et-point-point)
<!--toc:end-->

Linux est l'un des systèmes d'exploitation les plus populaires. Son développement
a été initié par Linux Torvalds en 1991. Le système d'exploitation s'est inspiré
de Unix, un autre système d'exploitation développé dans les années 1970 par les
laboratoires AT&T.

## Distributions

Une distribution Linux est un ensemble qui se compose d'un noyau Linux et d'une
sélection d'applications qui sont maintenues par une entreprise ou une communauté
d'utilisateurs. L'objectif d'une distribution et d'optimiser le noyau et les
applications qui sont exécutées sur le système d'exploitation pour un certain
usage ou groupe d'utilisateurs.

## Système d'exploitation UNIX

UNIX est un système d'exploitation: ouvert, portable et disponible.

### Caractéristiques du système UNIX

- Unix est système d'exploitation **multi-tâches**: plusieurs processus, également
  appelées *tâches*, peuvent être exécutées simultanément.

- Unix est un système d'exploitation **multi-utilisateurs** (multi-user): plusieurs
  utilisateurs peuvent utiliser le système en même temps (les ressources sont
  réparties entres les différents utilisateurs). Chaque utilisateur dispose de
  l'ensemble des ressources du système

Unix présente une interface utilisateur interactive et simple à utiliser: le
**shell**. Cette interface fournit des services de haut niveau. Elle intègre
un langage de commandes très puissant (scripts shell).

Linux concède deux interfaces: interface graphique et interface ligne de commande.

## Connexion et déconnexion

  **L'administrateur système appelé aussi *root***, utilisateur privilégié ou
super utilisateur (super user). Il dispose de tous les droits sur la machine
et le système Unix. Il s'occupe de l'administration du système, en particulier
il crée les comptes des utilisateurs.

  **L'utilisateur normal** dispose des droit réduits qui sont définis par l'administrateur
système.

**Unix associe à chaque utilisateur (un compte):**

- Un nom d'utilisateur ou nom de connexion (appelé *login*).
- Un mot de passe (password en anglais),
- Un home Directory (répertoire de l'utilisateur ou répertoire de connexion),
- Un language de commandes (shell)

> [!ATTENTION]
> Unix fait la différence entre les minuscules et des MAJUSCULES.

## Introduction à la notion de système de fichiers file system

### Notion de fichier et de répertoire

Le fichier est la plus petit entité logique de stockage permanent sur un disque
ou d'autres supports physiques. Il peut contenir du texte, des données,
programmes images. Où des programmes stock;es sur un disque. Les fichiers sont
classés dans des répertoires (catalogues). Chaque répertoire peut contenir
d'autres sous-répertoires, formant ansi une organisation arborescente.

### Nomenclature des fichiers

Le nom d'un fichier sous Unix est une suite de caractères, l'extension n'indique
pas le type de fichier, par exemple, un exécutable n'a pas besoin d'avoir une
extension particulière. Un fichier qui a l'extension *.exe*, ne veut pas dire
que c'est un fichier exécutable. En Fait le caractère *.* est considéré comme un
caractère qui fait parti du nom du fichier.

### Les différents types de fichiers

- les fichiers ordinaires
- Les répertoires (les fichiers répertoire)
- Les fichiers spéciaux

### Système de fichiers

Un système de fichier (File System en anglais), appelé aussi système de gestion
de fichiers, est une structure de donnée qui définit l'organisation d'un disque
(ou partition d'un disque).

> [!Note]
> **/** c'est le répertoire racine.

#### Quelques principaux répertoires Unix

Chaque fichier Unix est placé dans l'arborescence de racine **/** (désigne le
répertoire **root**) qui contient les sous répertoires suivants:

- **/root**: répertoire de l'administrateur root
- **/tmp**: contient les fichiers temporaires
- **/bin**: utilitaire de bas-niveau (exécutables essentiels pour le système)
- **/home**: répertoire pour les utilisateurs. Chaque utilisateur possède son
propre répertoire qui a le nom de son login.
- **/var**: fichiers dont le contenue varie
- **/lib**: contiens des bibliothèques partagées essentielles au systèmes lors
du démarrage...

#### Les répertoires *point* et *point point*

Quand on crée un répertoire, le système génère automatiquement deux sous répertoires,
du répertoire créé, qui sont:

- Le répertoire **.** qui représente un lien vers le répertoire créé.
- Le répertoire **.\.** qui représente un lien vers le répertoire père.

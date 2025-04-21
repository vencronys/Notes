---
id: shell-prog
Topics:
  - shell programming
tags:
  - linux
  - shell
  - programming
---

Class: [[linux]]
Date: 2025-04-14

# Variables du shell

## 1. Notion de variable

Une variable est une donnee identifier par un nom. le nom d'une variable est une suite de caracteres alphanumeriques.

## 2. Sous Unix, on distingue des types de variab;es:

- Variables locales (definies par l'utilisateur).
- Variables d'environnement (variables globales ou exportees).

**Une variable local** est specifique au processus shell en cours, elle ne sera pas disponible pour tous les processus fils crees.
**Les variables d;environnement** sont transmises aux sous-shells c'est a dire aux processus lances par le shell (proc fils du shell).

## 3. Utilisation des variables

Pour acceder a la valeur (au contenu) d'une variable, on la precede par le symbole `$`.

> [!Syntaxe]
> `var=valeur`
> `echo $var`

## 4. Destruction d'une variable

La commande `unset` permet de detruire une variable

> [!Syntaxe]
> `unsett nom_variable`

## 5. Commande `readonly`: protection d'une variable

Pour proteger la modification du contenu d'une variable on utilise la commande `readonly`.

> [!Syntaxe]
> `readonly var`

## 6. les alias

Un alis et une variable qui sert a :
- redefinir le nom d'une commande
- on a lui donner un nouveau nom.
Ceci permet de donner des noms simples a des commandes. 

> [!Syntaxe]
> `alias nom=commande`

La commande `unalias` Pour rendre une variable alias inaccessible.

## 7. Exportation de variables: commande `export`

make a local var into a global.

## 8. Les parametres speciaux

Ce sont en fait des variables reservees. Certaines de ces variables sont liees aux arguments passes au script shell. Pour les utiliser, on les fait preceder par le caractere specile `$` ces parametres sont:

- La variable reserve `0`: `$0` desinge le nom du script shell.
- Le parametre `*`: `$*` renvoie la liste de tous les arguments mais sous la forme d'un seul argument.
- Le parametre `?`: `$?` renvoie le code retour de la derniere commande.
- Le parametre `$`: `$$` renvoie le PID du processus qui execute le script (Le PID du sous-shell lance par le shell en cours pour executer le script).
- Le parametre `!`: `$!` renvoie le PID du processus lance pour executer la dernier commande lancee en arriere plan.
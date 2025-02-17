# Introduction à l'interpréteur de commandes le shell

<!--toc:start-->
- [Introduction à l'interpréteur de commandes le shell](#introduction-à-linterpréteur-de-commandes-le-shell)
  - [Définition](#définition)
  - [Syntaxe d'une commande](#syntaxe-dune-commande)
<!--toc:end-->

## Définition

Le shell est un programme (un fichier exécutable) qui a la charge d'analyser
les commandes que vous tapez dans un terminal.

- Il lit et interprète les commandes que vous tapez.
- Il transmet ces commandes au système d'exploitation pour qu'il les exécute.
- Il affiche les résultats de ces commandes.

## Syntaxe d'une commande

```bash
nom_commande [option1] [option2] ... [argument1] [argument2] ...
```

## Types des commandes

Le shell est un processus, qui s'exécute sur la machine. Quand une commande est
saisie: Soit le shell la reconnaît et l'exécute lui-même, soit il la transmet
quand elle est une commande externe, à un programme qui se trouve dans un
répertoire du système d'exploitation.

- Dans le cas des commandes internes, il n'y a pas de création de processus
  supplémentaire/fils.

- Dans le cas des commandes externes, le shell crée un processus fils pour
  exécuter la commande, le shell ne pourra pas exécuter une nouvelle commande
  qu'après la fin de l'exécution de la commande en cours ou du processus fils.

## Les commandes liées a l'environnement

- `echo` : Affiche un message à l'écran.
- `pwd` : Affiche le répertoire courant.
- `cd` : Change de répertoire.
- `ls` : Liste le contenu d'un répertoire.
- `mkdir` : Crée un répertoire.
- `rmdir` : Supprime un répertoire.
- `cp` : Copie des fichiers.
- `mv` : Déplace des fichiers.
- `rm` : Supprime des fichiers.
- `cat` : Affiche le contenu d'un fichier.
- `more` : Affiche le contenu d'un fichier page par page.
- `less` : Affiche le contenu d'un fichier page par page.
- `head` : Affiche les premières lignes d'un fichier.
- `tail` : Affiche les dernières lignes d'un fichier.
- `touch` : Crée un fichier vide.
- `file` : Détermine le type d'un fichier.
- `find` : Recherche des fichiers.
- `locate` : Recherche des fichiers.
- `which` : Recherche un exécutable dans le PATH.
- `whereis` : Recherche un exécutable dans les répertoires standards.
- `type` : Indique si une commande est interne ou externe.
- `alias` : Crée un alias pour une commande.
- `lsb_release` : Affiche des informations sur la distribution Linux.
- `uname` : Affiche des informations sur le système.
- `env` : Affiche les variables d'environnement.
- `export` : Exporte une variable d'environnement.
- `unset` : Supprime une variable d'environnement.
- `printenv` : Affiche les variables d'environnement.
- `set` : Affiche les variables d'environnement.
- `source` : Exécute un script dans le shell courant.
- `hostname` : Affiche le nom de la machine.
- `hostnamectl` : Affiche des informations sur la machine.
- `uptime` : Affiche le temps d'activité de la machine.
- `who` : Affiche les utilisateurs connectés sur la même machine.
- `whoami` : Affiche le nom de l'utilisateur courant.
- `w` : Affiche les utilisateurs connectés.
- `last` : Affiche les dernières connexions.
- `ps` : Affiche les processus en cours d'exécution.
- `top` : Affiche les processus en cours
- `kill` : Tue un processus.
- `logname` : Affiche le nom de l'utilisateur courant.
- `su` : Change d'utilisateur.
- `sudo` : Exécute une commande en tant qu'un autre utilisateur.
- `chown` : Change le propriétaire d'un fichier.
- `chmod` : Change les permissions d'un fichier.
- `umask` : Change les permissions par défaut.
- `passwd` : Change le mot de passe d'un utilisateur.
- `groups` : Affiche les groupes d'un utilisateur.
- `id` : Affiche les informations sur un utilisateur.
- `whois` : Affiche des informations sur un domaine.
- `date` : Affiche la date et l'heure.
- `cal` : Affiche le calendrier.
- `time` : Affiche le temps d'exécution d'une commande.
- `sleep` : Attend un certain temps.
- `watch` : Exécute une commande périodiquement.
- `clear` : Efface l'écran.
- `reset` : Réinitialise l'écran.
- `exit` : Quitte le shell.
- `logout` : Se déconnecte.
- `shutdown` : Arrête ou redémarre la machine.
- `reboot` : Redémarre la machine.
- `halt` : Arrête la machine.
- `poweroff` : Arrête la machine.
- `sync` : Synchronise les disques.
- `mount` : Monte un système de fichiers.
- `umount` : Démonte un système de fichiers.
- `df` : Affiche l'espace disque.
- `du` : Affiche l'espace disque utilisé.
- `free` : Affiche la mémoire libre.

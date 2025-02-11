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

# Les liens :

## Definition des liens :

**Puisqu'un fichier est identifie par son numero d'inode et non pas par son
nom de fichier**, il est possible de donner plusiers noms a un meme fichier
grace a la notion de lien : ceci pernet d'acceder au meme fichier a differents
endroits de l'arborescence

## Avantage :

- Possibilite d'acceder au meme fichier depuis des endroits et des noms differents
- Une seule copie sur le disque et plusieurs facons d'y acceder.
- Si l'un des fichiers est modifie, la meme modification est prise en compte
  par l'autre fichier.
- Simplifier l'acces a des fichiers dont les noms (chemin) sont difficiles a retenir.

## Types de liens

### Lien physique (hard link) :

**Un lien dur permet de donner plusieurs noms de fichiers qui ont le meme inode
(c'est dire des fichiers qui partage le nene contenu). Ceci

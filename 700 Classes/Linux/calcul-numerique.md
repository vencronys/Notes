# Calcul numerique sur les entiers

# La commande `expr`

### Syntaxe:

`expr expression`

>[!Exemple]
>```bash
>% expr 7 + 3
>ou
>% b = `expr $a + 1`
>ou
>% echo `expr $b/3`
>ou
>% a=2; b=4
>% d = `expr \($res+$a\)\*$b`
>% echo $d
>% 32
>```


## Evaluation arithmetique avec `(())`

### Syntaxe:

> [!Exemple]
> ```bash
> % a = 12
> % echo $((a +3)) ou % echo $(($a +3))
> 15
>```

## Evaluation arithmetique avec la commande `let`

### Syntaxe:

`let var=expression`

> [!Exemple]
> ```bash
> % let a=1+2; echo $a
> 3
> % a=8
> % let var=(2+$a)*5 ou % let var=(2+a)*5
>```


## Les Tests

### Les tests numeriques

#### Syntaxe:

`test nombre relation nombre` ou `[nombre relation nombre]`

#### Les relations sont :
- `-lt`: lower than
- `-le`: lower or equal
- `-gt`: greater than
- `-ge`: greater or equal
- `-eq`: equal
- `-ne`: not equal

> [!Exemple]
> `[$n1 -eq $n2]`


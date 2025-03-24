# Regex

Les expressions regulieres permettent de rechercher, filtrer ou modifier du texte en utilisant des motifs precis.

**Syntaxe de base**

| Symbole | Signification                                         | Exemple                                            |
| ------- | ----------------------------------------------------- | -------------------------------------------------- |
| `.`     | N'importe quel caractere sauf un retour a la ligne    | `a.b` => correspond a `acb`, `a3b`, ..             |
| `^`     | Debut d'une ligne                                     | `^Hello` => correspond a `Hello` en debut de ligne |
| `$`     | Fin d'une ligne                                       | `end$` => correspond a `end` en fin de ligne       |
| `*`     | Repete 0 ou plusieirs fois le caractere precedent     | `a*b` => `b`, `ab`, `aaab`, ...                    |
| `+`     | Repete 1 ou plusieurs fois le caractere precedent     | `a+b` => `ab`, `aaab` mais pas `b`                 |
| `?`     | Rend le caractere precedent optionnel (0 ou 1 fois)   | `colou?r`=> `color` ou `colour`                    |
| `{n}`   | Repete exactement n fois                              | `a{3}` => `aaa`                                    |
| `{n,}`  | Au moins n repetitions                                | `a{2,}` => `aa`, `aaa`, ...                        |
| `{n,m}` | Entre n et m repetitions                              | `a{2,4]` => `aa`, `aaa`, `aaaa`                    |
| `[]`    | Classe de caracteres                                  | `[aeiou]` => n'import quel voyelle                 |
| `[^]`   | Exclure une classe                                    | `[^0-9]` => n'importe quelle voyelle               |
| `\d`    | Chiffre (`[0-9]`)                                     | `\d+` => `123`, `456`, ...                         |
| `\D`    | Tout sauf un chiffre (`[^0-9]`)                       |                                                    |
| `\w`    | Lettre, chiffre ou \_ (`[a-zA-Z0-9_]`)                |                                                    |
| `\W`    | Tout sauf une lettre, chiffre ou \_ (`[^a-zA-Z0-9_]`) |                                                    |
| `\s`    | Espace, tabulation, saut de ligne                     |                                                    |
| `\S`    | Tout sauf un espace                                   |                                                    |
| `()`    | Groupe capturant                                      | OU logique `(ab)+` => `ab`, `abab`, ..             |
| `\b`    | Delimiteur de mot                                     | `\bchat\b` => `chat` mais pas `chateau`            |

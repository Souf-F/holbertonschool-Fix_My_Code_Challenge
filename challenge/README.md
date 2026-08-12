# Fix My Code Challenge

Ce dépôt regroupe une série d'exercices de correction de bugs dans différents langages (Python, JavaScript, Ruby, C). Chaque script contient une erreur volontaire à identifier et corriger.

## Sommaire

- [0. FizzBuzz](#0-fizzbuzz)
- [1. Print Square](#1-print-square)
- [2. Sort](#2-sort)
- [3. User Model](#3-user-model)
- [4. Delete Dnodeint at Index](#4-delete-dnodeint-at-index)

## 0. FizzBuzz

**Langage** : Python
**Fichier** : `0-fizzbuzz.py`

Programme qui affiche les nombres de 1 à n, en remplaçant les multiples de 3 par "Fizz", les multiples de 5 par "Buzz", et les multiples de 3 et 5 par "FizzBuzz".

Bug corrigé : l'ordre des conditions dans le `if/elif` faisait que le cas "multiple de 3" était testé avant le cas "multiple de 3 et 5", empêchant "FizzBuzz" de s'afficher pour les multiples de 15. La condition la plus spécifique doit être testée en premier.

Utilisation :
```
./0-fizzbuzz.py 89
```

## 1. Print Square

**Langage** : JavaScript
**Fichier** : `1-print_square.js`

Affiche un carré de caractères `#` dont la taille est donnée en argument.

Bug corrigé : `parseInt(process.argv[2], 16)` interprétait l'argument en base hexadécimale au lieu de la base décimale, faussant le résultat pour certaines valeurs (10 devenait 16). Remplacé par `parseInt(process.argv[2], 10)`.

Utilisation :
```
./1-print_square.js 8
```

## 2. Sort

**Langage** : Ruby
**Fichier** : `2-sort.rb`

Trie par ordre croissant les arguments numériques passés en ligne de commande, en ignorant les valeurs non entières.

Bug corrigé : lors de l'insertion d'un élément à la bonne position, `result.insert(i - 1, i_arg)` utilisait un mauvais indice. Quand l'élément devait être inséré en tête de liste (i = 0), l'indice -1 insérait avant le dernier élément au lieu du premier. Remplacé par `result.insert(i, i_arg)`.

Utilisation :
```
ruby 2-sort.rb 12 41 2 C 9 -9 31 fun -1 32
```

## 3. User Model

**Langage** : Python
**Fichier** : `3-user.py`

Classe `User` avec un identifiant unique et un mot de passe stocké sous forme de hash MD5.

Bugs corrigés :
- le setter assignait la valeur à `self._password` (simple underscore) au lieu de `self.__password` (double underscore), créant un attribut différent de celui lu par le getter
- la méthode `is_valid_password` comparait le hash en majuscules (`.upper()`) alors que le setter stockait le hash en minuscules (`.lower()`), rendant la comparaison toujours fausse

Utilisation :
```
./3-user.py
```

## 4. Delete Dnodeint at Index

**Langage** : C
**Dossier** : `4-delete_dnodeint/`
**Fichier** : `delete_dnodeint_at_index.c`

Fonction qui supprime un noeud d'une liste doublement chaînée d'entiers, à un index donné.

Statut : en cours de correction.

## Structure du dépôt

```
.
├── 0-fizzbuzz.py
├── 1-print_square.js
├── 2-sort.rb
├── 3-user.py
├── 4-delete_dnodeint/
│   └── delete_dnodeint_at_index.c
└── README.md
```

## Remarques générales

Certains scripts nécessitent le bit d'exécution pour être lancés directement (`./nom_du_fichier`). En cas d'erreur "Permission denied", appliquer :
```
chmod +x nom_du_fichier
```

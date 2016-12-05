# SimplonStrap

## Voir la Doc : https://simplonmars3.github.io/SimplonStrap/

### Elements Finalisés :
- Reset User Agents
- Grille en Flex
- Grille sans Flex en base 12
- Formulaire
- Tableaux

### Elements en cours de développement :
- Barre de Navigation // Menu
- Helper Class
- Font Icons avec Fontello (pour toute demande Voir Issue #4)
-
-

### Bugs en cours :
- Probleme Balise Code sur index.html

### Bonnes Pratiques : 
- Lors d'un Pull Request : Proposez du code !! (dans la mesure du possible )
- Lorsqu'une de vos Pull Request et Issues sont acceptés vous pouvez retrouver la modification après le merge portant le nom #fix+numeropullrequest

## Dimanche 4/12/16 - Mise à jour de la Grille sans Flex :

Bonjour, Changements dans SimplonStrap :

Comme vous avez pu le constater, les largeurs de colonnes ne fonctionnent que si elles sont dans le grid container. Donc pas moyen de les utiliser, à moins de créer une autre classe de largeurs en pourcentage... 

Du coup, j'ai rendu ces classes universelles, histoire qu'on puisse les utiliser même en dehors de la grille (on a déjà quelques largeurs, mais la plupart ne fonctionne qu'à l'intérieur).

Cela corrige également le problème des autres largeurs relatives en dehors de la grille étant en {float: left;} par défaut.

Pour vous montrer, on passe de ça :

```
*[class*="w-"], *[class*="-twelve"] {
  float: left;
  padding: 10px;
}
/* Grid Widths */
/*--1/12--*/
.grid .one-twelve, .grid .w-1-12 {
    width: calc(100%/12);
}
```

etc...


À ça :

```
.grid *[class*="w-"], .grid *[class*="-twelve"] {
  float: left;
  padding: 10px;
}
/* Grid Widths */
/*--1/12--*/
.one-twelve, .w-1-12 {
    width: calc(100%/12);
}
```


J'en profite pour ajouter + de largeurs en pourcentage.

Du coup, plus de liberté pour les largeurs dans ET hors de la grille, vu que vous pourrez ajouter des multiple de 5, etc.

Pour ceux vous qui utiliserez ces classes, ça change rien au final, vous aurez juste plus de possibilités.

Bref, j'attends vos retours en cas de problème ou autre ;)

Pour rappel, la classe container .grid :

```
.grid {
    display: block;
    clear: both;
    overflow: auto;
}
```

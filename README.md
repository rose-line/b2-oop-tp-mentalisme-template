
# TP Mentalisme

## Introduction

Dans ce TP, vous allez modéliser en Programmation Orientée Objet une simulation d'un tour de mentalisme où le magicien devine une carte pensée par un spectateur, sans jamais la voir ni la toucher. Ce tour met en scène un magicien mentaliste, son assistant, un spectateur, et un jeu de cartes.

## Description de la solution

Le tour se déroule ainsi :

1. Le spectateur choisit secrètement une carte dans un jeu (valeur et couleur), puis la note sur un papier.
2. L'assistant récupère le papier, encode la carte en une phrase selon un procédé secret : il utilise un mot ou une expression pour le rang, et un mot ou une expression pour la couleur, puis annonce mine de rien la phrase au magicien.
3. Le magicien, connaissant le procédé d'encodage, décode la phrase et annonce la carte pensée par le spectateur.

Vous devez modéliser les classes suivantes :

- `Magicien`
- `Assistant`
- `Spectateur`
- `Papier`
- `Carte`

Chaque classe doit avoir des attributs privés et des méthodes adaptées à son rôle. Privilégiez l'encapsulation, ne créez des getters/setters que si nécessaire. Les constructeurs doivent permettre d'initialiser les objets selon le déroulement du tour.

Pour la classe `Spectateur`, prévoyez deux constructeurs :

- Un constructeur non paramétré qui demande à l'utilisateur de choisir une carte via le terminal.
- Un constructeur paramétré (valeur et couleur reçues en paramètres).

Vous testerez les deux constructeurs dans votre code client.

## Tableaux de correspondance

Pour encoder la carte, l'assistant utilise les tableaux suivants (vous pouvez le modifier si vous le souhaitez) :

**Rang**

| Rang   | Mot/Expression |
| ------ | -------------- |
| As     | "Super"        |
| Deux   | "Parfait"      |
| Trois  | "Nickel"       |
| Quatre | "Excellent"    |
| Cinq   | "Formidable"   |
| Six    | "Splendide"    |
| Sept   | "Magnifique"   |
| Huit   | "Impeccable"   |
| Neuf   | "Bon choix"    |
| Dix    | "Fantastique"  |
| Valet  | "Bien choisi"  |
| Dame   | "Voilà"        |
| Roi    | "OK"           |

**Couleur**

| Couleur | Mot/Expression           |
| ------- | ------------------------ |
| Trèfle  | "à vous !"               |
| Carreau | "maître ?"               |
| Cœur    | "la réponse du maître ?" |
| Pique   | "c'est à vous, maître !" |

L'assistant annonce la phrase composée du mot/expression du rang suivi du mot/expression de la couleur, par exemple :

> "Voilà, la réponse du maître ?" (Dame de Coeur)
> "OK, c'est à vous, maître !" (Roi de Pique)
> "Parfait, à vous !" (Deux de Trèfle)

## Exemple d'exécution

```
--- Exemple 1 : saisie utilisateur ---
[Spectateur] Je choisis une carte dans le jeu.
[Spectateur] Entrez le rang (ex: Dame ou 9) : Dame
[Spectateur] Entrez la couleur (trèfle, carreau, coeur, pique) : Coeur
[Spectateur] J'ai choisi : Dame de Coeur
[Spectateur] J'écris la carte sur le papier et je donne le papier à l'assistant.
[Assistant] Je prends le papier et j'encode la carte...
[Assistant] J'annonce : Voilà, la réponse du maître ?
[Magicien] Je pense à.... Dame de Coeur !

--- Exemple 2 : paramètres ---
[Spectateur] J'ai choisi : Dame de Coeur
[Spectateur] J'écris la carte sur le papier et je donne le papier à l'assistant.
[Assistant] Je prends le papier et j'encode la carte...
[Assistant] J'annonce : OK, c'est à vous, maître !
[Magicien] Je pense à... Roi de Pique !
```

## Conseils

- Réfléchissez bien aux attributs : _qui a quoi comme données (état) ?_
- Et aux méthodes : _qui fait quoi ?_ Il faudra demander le rang et la couleur de la carteau spectateur, écrire sur un papier, montrer le papier à l'assistant, lire le papier, etc. Toutes ces actions sont de potentiels indices pour définir des méthodes de certaines classes.
- Mais même pour cette petite simulation, il y a de multiples variantes d'implémentation possibles. Il n'y a pas de solution unique.
- C'est votre code client qui va vous indiquer si votre modélisation est plutôt bonne et cohérente : si le code client se lit un peu comme le déroulement du tour et s'adresse à chaque fois aux objets concernés, ça veut dire que que l'implémentation de vos classes est probablement cohérente.
- Commencer par le code client, puis implémenter les classes : qu'aimeriez vous écrire pour la première phase du tour dans votre code client ? Implémentez la classe correspondante pour répondre à ce besoin.
- Travaillez étape par étape, testez rapidement et régulièrement.

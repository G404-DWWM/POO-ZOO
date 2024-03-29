# TP PooZoo 🦁

## Objectif 🚀

Bienvenue dans ce TP où je vous propose de créer un petit zoo et de le gérer. L’objectif est de vous faire travailler avec les classes et l’héritage. Dans un premier temps, comme pour le TP QCM, vous ferez fonctionner votre code sans BDD. Puis, vous utiliserez PDO pour lier vos classes à une nouvelle BDD qui correspondra à vos classes. C’est à vous d’imaginer dans un premier temps la structure des données, la structure de vos classes et leur management. Utilisez la correction du QCM pour vous inspirer. Commencez en faisant simple puis montez en complexité dans votre projet.

## Description du Zoo 🏞️

- Le zoo est constitué de plusieurs enclos et chaque enclos peut contenir jusqu’à 6 animaux.
- Dans un enclos, tous les animaux doivent être de la même espèce (ex : les baleines avec les baleines, les aigles avec les aigles, ...). Cependant, il doit être possible de mettre n'importe quelle espèce dans n'importe quel enclos.
- Le zoo contient un employé, qui sert d'interface entre le zoo et vous (l'utilisateur du programme).
- Au travers de cet employé, vous pouvez donner à manger aux animaux, les transférer d'un enclos à un autre, nettoyer les enclos...

Ci-dessous, vous trouverez les spécifications minimales du programme pour chaque classe. Attention, elles sont parfois incomplètes. À vous de créer les classes, les propriétés et les méthodes supplémentaires dès que cela semble nécessaire.

## Les Animaux 🐅🐦🐠

Au minimum, le programme doit pouvoir créer 4 espèces : des Tigres, des Ours, des Poissons, et des Aigles.

Pour chaque espèce, nous devons pouvoir indiquer leur poids, taille, nom de l'espèce et âge. De plus, des booléens seront utilisés pour déterminer si l'animal a faim, s'il dort, s'il est malade.

Au niveau des méthodes, en plus des accesseurs et mutateurs habituels, chaque animal doit pouvoir manger, émettre un son, être soigné, dormir ou se réveiller. Il faut aussi une méthode pour afficher toutes ses caractéristiques.

Les Tigres doivent pouvoir vagabonder. Les animaux marins doivent pouvoir nager et les animaux volants doivent pouvoir voler.

**En utilisant une hiérarchie d'héritage et d’encapsulation, écrivez des classes pour chacun de ces animaux.**

## 🌋 Les Enclos

Chaque enclos peut contenir jusqu’à 6 animaux.

Dans un enclos, tous les animaux doivent être de la même espèce (ex : les baleines avec les baleines, les aigles avec les aigles, ...). Cependant, il doit être possible de mettre n'importe quelle espèce dans n'importe quel enclos (sauf pour les volières et les aquariums). 

Tous les enclos possèdent les caractéristiques suivantes : un nom, un degré de propreté (pouvant prendre comme valeur : mauvaise, correcte, bonne) et le nombre d'animaux présents. Outre les accesseurs et mutateurs, les méthodes d'un enclos doivent permettre :
- d'afficher ses caractéristiques,
- d'afficher les caractéristiques des animaux qu'il contient,
- d'ajouter et d'enlever des animaux dans l'enclos,
- d'entretenir l'enclos si celui-ci est vide.

On distinguera deux sous-classes d'enclos particulier : les volières et les aquariums.

Une volière ne peut contenir que des animaux volants. En plus des caractéristiques communes à tous les enclos, elle possède aussi une hauteur. L'entretien de ce type d'enclos nécessite aussi la vérification du sommet de la cage.

Similairement, un aquarium ne peut contenir que des animaux aquatiques. Un aquarium possède une variable supplémentaire, la salinité de l'eau. L'entretien d'un aquarium nécessite la vérification de la salinité de l'eau.

**Ecrivez les classes correspondant aux trois types d'enclos.**

## 👷 L'Employé

L'employé possède les caractéristiques suivantes : le nom de l'employé, son âge, son sexe.

Outre les constructeurs, accesseurs et mutateurs nécessaires, les méthodes suivantes, entre autres, doivent permettre :

1. À l'employé d'examiner un enclos, Cette méthode affiche les animaux contenus dans l'enclos, ainsi que les caractéristiques de l'enclos,
2. De nettoyer un enclos si l'enclos est sale et vide,
3. De nourrir les animaux d'un enclos lorsqu'ils ne dorment pas,
4. D’ajouter à un enclos un nouvel animal lorsque c'est possible,
5. D'enlever un animal d'un enclos,
6. De transférer un animal d'un enclos à un autre.

Enfin, l'employé possède une dernière méthode qui constitue l'interface avec l'utilisateur. À l'aide d'un menu (un formulaire), l'utilisateur doit pouvoir diriger l'employé.

**Écrivez la classe correspondant à l'employé.**

## Le Zoo

La classe `Zoo` représente le zoo dans votre programme. Un zoo possède les caractéristiques suivantes :
- Nom du zoo
- Un employé
- Un nombre maximal d'enclos
- Un tableau d'enclos

### Méthodes

Les méthodes d'un zoo permettent :

1. D'afficher le contenu de tous les enclos,
2. Et d'afficher le nombre d'animaux présents dans le zoo.
3. Enfin le zoo contient aussi la méthode `main()`. Le comportement d ela méthode `main()` est le suivant. Dans une boucle `while` :
    - Pour chaque animal du zoo, on va aléatoirement modifier les valeurs des variables d'instance de cet animal (par exemple on le rend malade, on l'endort ou on l'affame).
    - Pour chaque enclos, on modifie aléatoirement son état de propreté, sa salinité, etc...
    - Enfin on passe la main à l'employé (donc à vous, utilisateur) pour qu'il s'occupe du zoo.

**Écrivez la classe correspondant au zoo.**

## Pour aller plus loin...

Pour enrichir votre simulation de zoo, voici quelques idées supplémentaires que vous pouvez implémenter :

1. **Nouvelles espèces :**
   - Ajoutez de nouvelles espèces telles que vautour, serpent, dauphin, etc.
   - Distinguez les espèces par leur habitat (marin, terrestre, volant).

2. **Classification des espèces :**
   - Classez les espèces selon un ordre animal (mammifères, ovipares, etc.).

3. **Cycle de vie des espèces :**
   - Introduisez un âge de maturité et un âge maximal pour chaque espèce.

4. **Genre et reproduction :**
   - Déterminez le sexe des animaux (mâle ou femelle).
   - Permettez aux animaux de s'accoupler sous certaines conditions (présence d'un partenaire du sexe opposé et de la même espèce).

5. **Reproduction spécifique :**
   - Implémentez une reproduction différente pour les espèces ovipares (pondre un œuf immédiatement) et pour les mammifères (gestation avec une durée variable).

6. **Développement des œufs :**
   - Modélisez le développement de l'œuf jusqu'à maturité, puis son éclosion en un nouvel animal.

7. **Évolution temporelle :**
   - À chaque rechargement de la page index, faites évoluer le temps dans le zoo.
   - Les animaux mûrissent, s'accouplent, atteignent leur âge maximal et décèdent.
   - La gestation des mammifères progresse.
   - Le développement de l'œuf avance.
   - La maladie des animaux évolue, entraînant la mort en l'absence de soins.

8. **D'autres mécanismes évolutifs :**
   - Ajoutez d'autres mécanismes évolutifs en fonction des caractéristiques spécifiques des animaux (ex : migration, changement de comportement, etc.).

Continuez à explorer et à ajouter des fonctionnalités pour rendre votre simulation de zoo encore plus réaliste et complexe. N'oubliez pas d'adapter ces idées en fonction de la structure actuelle de votre programme.



# Feedbacks #

## Retour global ##

### Appréciation générale ###

- Les notions abordées semblent très fragiles.
Il va falloir que tu consolides ces notions avant de pouvoir reprendre l'exercice, et pouvoir passer sereinement à la suite des modules.
Reprends les points de cours que je t'ai partagé à la fin de mes retours, puis essaye de le reprendre à tête reposée ;)

### problèmes techniques ###

- Connexion à la BDD
Il faut que tu reprennes la connexion à ta base de donnée au sein de ton fichier de configuration config.ini
Les paramètres username et password correspondent aux paramètres de connexion à ton SGBD, ces paramètres sont communs à tous tes projets, et ne doivent pas être identiques au nom de ta BDD.

- Oublie ErrorController et CoreController
Tu as oublié de créer tes controllers parents, auxquels tu fais référence au sein des tes Controlleurs enfants Teachers, Students et Users.

- Incohérence controller user / classe user
Ton controller user n'est pas cohérent avec la classe User que tu as mise en place.
Par exemple, au sein de ton controller user, tu cherches à stocker le prénom et le nom de ton utilisateur.
Cependant, ta classe user n'accepte qu'un champ nom global.

- Gestion des droits et accès
La gestion des droits et des accès ne semble bien maitrisée, cette notion doit être effectuée au sein de ton contrôller User.

## Routing ##

### Méthodologie ###

- Tu as paramétré l'ensemble de tes routes directement au sein de ton index.
Cela est fonctionnel, mais il est recommandé d'exporter tes routes au sein d'un fichier spécifique de ton répertoire app pour clarifier ton code au maximum.

## Point cours ##

### POO ###

La Programmation Orientée Objet (POO) est un concept clé en développement logiciel. C'est une façon de structurer le code en utilisant des classes et des objets. Une classe est comme un plan pour créer un objet, qui définit ses propriétés et ses comportements. Les propriétés sont des variables qui stockent les données de l'objet, tandis que les méthodes sont des fonctions qui permettent de manipuler ces données.

La POO permet de mieux organiser le code en séparant les responsabilités. Les classes peuvent être considérées comme des boîtes noires, qui exposent une interface claire pour les autres parties du code. Cela facilite la maintenance et l'évolution du code en permettant de modifier ou d'ajouter des fonctionnalités sans impacter le reste du code.

Pour mieux comprendre, prenons l'exemple d'une classe pour représenter une voiture. La classe pourrait définir les propriétés de la voiture, comme la marque, le modèle, la couleur, etc. Ensuite, elle pourrait définir les méthodes pour manipuler ces propriétés, comme démarrer la voiture, la faire avancer, la faire tourner, etc. En utilisant des objets, tu pourrais créer différentes voitures avec des valeurs différentes pour leurs propriétés.

En somme, la POO est un concept clé en développement logiciel qui permet de mieux organiser le code en utilisant des classes et des objets. Cela facilite la maintenance et l'évolution du code en séparant les responsabilités.

Exemple de création d'une classe voiture :

class Voiture {
    // Attributs
    public $marque;
    public $modele;
    public $annee;
    public $couleur;
    public $vitesse = 0;

    // Méthodes
    public function demarrer() {
        echo "La voiture démarre...";
    }

    public function accelerer($vitesse) {
        $this->vitesse += $vitesse;
        echo "La voiture accélère à " . $this->vitesse . " km/h...";
    }

    public function freiner() {
        $this->vitesse = 0;
        echo "La voiture freine et s'arrête...";
    }
}

Utilisation de cette classe voiture au sein d'un controller :

// Créer un objet voiture
$maVoiture = new Voiture();

// Modifier les attributs
$maVoiture->marque = "Renault";
$maVoiture->modele = "Clio";
$maVoiture->annee = 2010;
$maVoiture->couleur = "Noir";

// Appeler les méthodes
$maVoiture->demarrer();    // Affiche "La voiture démarre..."
$maVoiture->accelerer(50); // Affiche "La voiture accélère à 50 km/h..."
$maVoiture->freiner();     // Affiche "La voiture freine et s'arrête..."


### Héritage ###

L'héritage de classes est un concept de la programmation orientée objet qui permet à une classe d'hériter les propriétés et les méthodes d'une autre classe parente.
La classe enfant peut ainsi utiliser les propriétés et les méthodes de la classe parente, et peut également ajouter ses propres propriétés et méthodes spécifiques.

En PHP, l'héritage de classes est implémenté à l'aide du mot-clé "extends".
Pour créer une classe enfant qui hérite d'une classe parente, il suffit de définir la nouvelle classe en utilisant le mot-clé "class" suivi du nom de la nouvelle classe, suivi du mot-clé "extends" et du nom de la classe parente.

Voici un exemple d'héritage de classe : 

class Vehicule {
    public $marque;
    public $modele;
    public $annee;
    public $vitesse = 0;

    public function demarrer() {
        echo "Le véhicule démarre...";
    }

    public function accelerer($vitesse) {
        $this->vitesse += $vitesse;
        echo "Le véhicule accélère à " . $this->vitesse . " km/h...";
    }

    public function freiner() {
        $this->vitesse = 0;
        echo "Le véhicule freine et s'arrête...";
    }
}

class Voiture extends Vehicule {
    public $nbPortes;

    public function ouvrirToit() {
        echo "La voiture ouvre son toit panoramique...";
    }
}

class Moto extends Vehicule {
    public $nbRoues = 2;

    public function faireUnWheeling() {
        echo "La moto fait un wheeling...";
    }
}


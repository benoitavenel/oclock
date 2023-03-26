# Feedbacks #

## Retour global ##

### Appréciation générale ###

- C'est trop juste pour le moment
Tu as besoin de revoir les notions de rooting pour pouvoir avancer sereinement par la suite.
Reprends les points de cours que je t'ai partagé à la fin de mes retours, puis essaye de le reprendre à tête reposée ;)

### Reste à faire ###

Il te manque les fonctionnalités suivantes : 

- Gestion des accès
- Ajout, Modification et suppression des professeurs
- Ajout de la navbar sur l'ensemble des pages
- Modification et suppression des étudiants
- Affichage des utilisateurs

### Erreurs fonctionnelles ###

- Ajout étudiant
Lors de l'ajout des étudiants, tu as bien pensé à ajouter une vérification sur les champs de nom et de prénom, mais tu as oublié de l'ajouter sur les champs profs et status, c'est dommage !
Pense à ajouter un message d'aide à ton utilisateur si tu effectues une vérification et que celle ci n'est pas validée ( message de retour pour facilier l'UX de ton utilisateur )

- Ajout prof
L'ajout d'un professeur redirige vers l'ajout d'un nouvel étudiant. 
Fais attention lors de l'utilisation de tes routes à ne pas t'emmêler les pincaux ;) 

- Code student au sein du controller de teacher
Tu as du code de ton controller Studiant copier coller au sein du controller Teacher.
Je pense qu'il ne s'agit pas simplement d'un oubli, et que le principe des contrôlleurs et de la POO est à revoir.

## Routing ##

### Méthodologie ###

- Tu as paramétré l'ensemble de tes routes directement au sein de ton index.
Cela est fonctionnel, mais il est recommandé d'exporter tes routes au sein d'un fichier spécifique de ton répertoire app pour clarifier ton code au maximum.

### Liens navbar ###

- Une partie des liens de ta navbar n'utilisent pas le rooting
Tu as définis tes liens vers l'accueil, les utilisateurs et le logout en relatif, sans utiliser ton système de rooting.
Les pages .html auxquels tu fais référence n'existent pas, et redirigent donc vers des erreurs 404. 
Une fois mise en place, il est important d'utiliser ton rooteur pour l'ensemble des liens et redirections que tu effectues.
Attention à ne pas mélanger les notions étudiées ;)

### .htaccess ###

- Tu as oublié d'ajouter un .htaccess à la racine de ton répetoire public.
De ce fait, ton code est fonctionnel uniquement s'il est présent à la racine de ton serveur web.
Ce fonctionnement peut très bien fonctionner lorsque tu développes en local, mais risque de te poser des problèmes lors de passage sur serveur.
Pense à ajouter cette configuration pour prévenir les erreurs de redirection serveur.

## Point cours ##

### Rooting ###

Le rooting permet de faire correspondre des URL à des actions spécifiques de ton application.
Pour cela, il faut mettre en place un nouveau fichier "routes.php" au sein du répertoire App, qui définira les actions à effectuer en fonction des routes choisies.
Dans un premier temps, il faut créer un nouveau objet AltoRouter à l'aide de la commande suivante : $router = new AltoRouter();
Ensuite, tu peux paramétrer chacune de te routes à l'aide de la méthode map appliquée sur cet objet, en passant en paramètre le type de requête, le chemin de la route, et l'action à effectuer.
Par exemple :

/* $router->map('GET', '/', function() {
    echo 'Page d\'accueil';
}); */

Tu pourras ensuite rediriger ton utilisateur vers l'une de ces routes en utilisant la méthode generate sur ton objet router, et en lui passant en paramètre le nom de la route vers laquelle tu souhaites le rediriger : header('Location: '.$router->generate('home'));



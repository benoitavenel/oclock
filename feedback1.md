# Feedbacks #

## Retour global ##

### Appréciation générale ###

- C'est du très bon travail ! :)
Ton projet est presque entièrement fonctionnel, et ton code est très propre, félicitation
L'ensemble des notions semblent bien comprises, porte un peu plus d'attention à la propreté générale de ton code et à la lecture des consignes, et ce sera parfait ! :D

## Controllers ##

### Méthodes ###

- Les annotations de tes méthodes sont trop génériques, il est important que tu spécifies le rôle exacte de tes méthodes. 
Pour ta méthode teacherUpdateGet() par exemple, il serait plus pertinent de modifier ton annotation "edit a teacher" par "Méthode récupérant et affichant les informations d'un professeur pour modification".

## Routing ##

### Méthodologie ###

- Tu as paramétré l'ensemble de tes routes directement au sein de ton index.
Cela est fonctionnel, mais il est recommandé d'exporter tes routes au sein d'un fichier spécifique de ton répertoire app pour clarifier ton code au maximum.

### .htaccess ###

- Tu as oublié d'ajouter un .htaccess à la racine de ton répetoire public.
De ce fait, ton code est fonctionnel uniquement s'il est présent à la racine de ton serveur web.
Ce fonctionnement peut très bien fonctionner lorsque tu développes en local, mais risque de te poser des problèmes lors de passage sur serveur.
Pense à ajouter cette configuration pour prévenir les erreurs de redirection serveur.

## Permissions ##

### Accès ###

- La gestion des permissions est globalement bien comprise.
Tu as su restrindre l'accès des pages aux utilisateurs connectés, et gérer une différence d'accès entre les rôles admin et user.
Par contre, tu as trop restrinct les accès aux utilisateurs, qui n'ont pas la possibilité de visualiser les profs, c'est dommage ;) 
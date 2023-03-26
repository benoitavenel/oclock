# Explication Fetch #

## Notion théorique ## 

La Fetch est une fonction Javascript te permettant d'envoyer une requête HTTP ( requête API par exemple ) depuis le navigateur.
Elle permet de récupérer des données depuis un serveur distant sans avoir besoin de recharger ta page.
Par exemple, si tu veux récupérer des données depuis une API qui fournit des informations sur la météo, tu peux utiliser le fetch pour envoyer une requête au serveur de l'API et récupérer les données en temps réel pour les afficher au sein de ton site.

## Exemple pratique ##

Imaginons maintenant que ton projet soit déployé sur un serveur, accessible à l'adresse suivante : www.oclockTeam.fr
Tu as créé sur ce projet une méthode student() te permettant de récupérer la liste de tous tes étudiants.
Cette méthode est donc accessible sur le lien suivant : 
www.oclockTeam.fr/students/list

Tu peux, grâce à la méthode fetch, accéder à ces données dynamiquement et les utiliser au sein de ton code JS de cette façon :

fetch('https://www.oclockTeam.fr/students/list')
  .then(response => response.json())
  .then(data => {
    // Utilise les données récupérées depuis la méthode student()
    console.log(data);
  })
  .catch(error => {
    // Gère les erreurs éventuelles
    console.error(error);
  });
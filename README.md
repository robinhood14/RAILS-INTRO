# Découvrez Ruby on Rails ![alt text][logo]

1. La différence entre un site statique et un site dynamique
2. Le MVC
3. Les routes
4. Les Bases de Données
5. GET / POST
6. Le concept de migration
7. Les relations entre les models des BDD
<hr>
## Ruby On Rails , c'est quoi ? 
Ruby On Rails, c'est un framework écrit en Ruby pour faire des sites/app web. 
### 3 grand principes : 
###### Le DRY (Don't Repeat Yourself) : 
Rails encourage à ne pas écrire plusieurs fois le même code. Rendre réutilisable le code de vos applications est une bonne chose !
###### Convention over configuration: 
Rails se base uniquement sur des conventions, non sur de la configuration (à l'inverse d'autres langages comme Java par exemple). Si vous respectez ces principes de convention, vous rendrez votre code maintenable et vous gagnerez en productivité.
###### REST : 
c'est le meilleur design pattern pour le développement d'applications web. Il vous permet d'organiser vos applications autour de verbes HTTP standards.

<hr>
## Site statique ou site dynamique ?
<p> 
Lorsque vous tapez dans la barre d’adresse ou que vous cliquez sur un lien, vous demandez en fait à un serveur de vous afficher un document HTML qui est stocké à un endroit précis sur ce serveur. Le serveur obéit et vous renvoie ce fameux document que vous lui avez demandé. Il s'agit d'un site statique.
Dans un site dynamique, le processus est différent, le fichier HTML n’existe pas encore. Il va être généré en fonction de paramètres que vous allez lui envoyer.
Vous allez les lui envoyer soit de façon consciente, par exemple en remplissant un formulaire et en cliquant sur envoyer.  
Ex :  un formulaire de demande de devis, vous allez donner la quantité de produits désirée, le type de produit désiré et puis le serveur va recevoir ces paramètres et va traiter la demande.
Vous pouvez aussi le faire de façon inconsciente, c’est-à-dire en cliquant sur un lien. Ce lien a des paramètres qui se mettent dans l’url , le script a été fait pour comprendre ces paramètres,  et en fonction de ces paramètres il va créer un fichier HTML.



<hr>
## MVC 

<p> Plutot abstrait à définir concretement, le MVC est un principe d’organisation de code basé sur la répartition suivante : </p>
<p> align="center"> Vue  - modele  - controleur </p>

###### Vue : cette partie du code gère l'affichage. 
La vue, c’est de la présentation. C’est comment on veut que la donnée soit présentée à l’utilisateur. Ça peut être le code qui pond du HTML et CSS, ou fait configurer de jolis boutons dans une UI par exemple.
###### Modèle : cette partie du code gère la manipulation des données.
Le modèle manipule la donnée. Dans un site Web, le modèle est souvent le code qui permet de faire de requêtes à la base de données. 
###### Controleur : en gros , c'est tout le reste. 
Il fait le lien ente le modele et la vue et renvoie la page a l'utilisateur. L’espèce de truc machin qu’on va mettre en place pour faire marcher le programme, c’est le contrôleur.
<div> 
</p>

<p align="center">
<img src= http://csharpcorner.mindcrackerinc.netdna-cdn.com/article/generate-a-controller-and-view-in-ruby-on-rails/Images/image001.jpg target="_blank"> 
</p>


[logo]: https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/Ruby_On_Rails_Logo.svg/200px-Ruby_On_Rails_Logo.svg.png "Ruby On Rails"

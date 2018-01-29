# Découvrez Ruby on Rails ![alt text][logo]

#### Ruby On Rails , c'est quoi ? 
Ruby On Rails, c'est un framework écrit en Ruby pour faire des sites/app web. 
3 grand principes : 
- Le DRY (Don't Repeat Yourself) : 
Rails encourage à ne pas écrire plusieurs fois le même code. Rendre réutilisable le code de vos applications est une bonne chose !
- Convention over configuration: 
Rails se base uniquement sur des conventions, non sur de la configuration (à l'inverse d'autres langages comme Java par exemple). Si vous respectez ces principes de convention, vous rendrez votre code maintenable et vous gagnerez en productivité.
- REST : 
c'est le meilleur design pattern pour le développement d'applications web. Il vous permet d'organiser vos applications autour de verbes HTTP standards.
### Site statique ou site dynamique ?
<hr>
Lorsque vous tapez dans la barre d’adresse ou que vous cliquez sur un lien, vous demandez en fait à un serveur de vous afficher un document HTML qui est stocké à un endroit précis sur ce serveur. Le serveur obéit et vous renvoie ce fameux document que vous lui avez demandé. Il s'agit d'un site statique.
<div> 
<p>
Dans un site dynamique, le processus est différent, le fichier HTML n’existe pas encore. Il va être généré en fonction de paramètres que vous allez lui envoyer.
Vous allez les lui envoyer soit de façon consciente, par exemple en remplissant un formulaire et en cliquant sur envoyer.  
Ex :  un formulaire de demande de devis, vous allez donner la quantité de produits désirée, le type de produit désiré et puis le serveur va recevoir ces paramètres et va traiter la demande.
Vous pouvez aussi le faire de façon inconsciente, c’est-à-dire en cliquant sur un lien. Ce lien a des paramètres qui se mettent dans l’url , le script a été fait pour comprendre ces paramètres,  et en fonction de ces paramètres il va créer un fichier HTML.

</p>
</div>
<p align="center">
    <img src=" https://www.google.fr/search?biw=1012&bih=615&tbm=isch&sa=1&ei=mkRvWsrvGpKkwAK4_Za4Dw&q=diff%C3%A9rence+between+a+static+website+and+a+dynamic+website&oq=diff%C3%A9rence+between+a+static+website+and+a+dynamic+website&gs_l=psy-ab.3...31093.45863.0.46729.47.46.0.0.0.0.326.5104.16j15j4j2.37.0....0...1c.1.64.psy-ab..10.2.266...0j0i8i30k1j0i24k1.0.-vD_-Ym5FLQ#imgrc=zYdeDh1i4IdvbM:">
</p>

### Le MVC
<hr>
<p> Plutot abstrait à définir concretement, le MVC est un principe d’organisation de code basé sur la répartition suivante : 

**La vue** cette partie du code gère l'affichage. 
La vue, c’est de la présentation. C’est comment on veut que la donnée soit présentée à l’utilisateur. Ça peut être le code qui pond du HTML et CSS, ou fait configurer de jolis boutons dans une UI par exemple.
**Le modèle** cette partie du code gère la manipulation des données.
Le modèle manipule la donnée. Dans un site Web, le modèle est souvent le code qui permet de faire de requêtes à la base de données. 
**Le contrôleur** en gros , c'est tout le reste. 
Il fait le lien ente le modele et la vue et renvoie la page a l'utilisateur. L’espèce de truc machin qu’on va mettre en place pour faire marcher le programme, c’est le contrôleur.
<a href="https://www.supinfo.com/articles/single/1625-mvc-presentation-patron-conception" target="_blank">Source</a>
<p>

<p align="center">
<img src= http://csharpcorner.mindcrackerinc.netdna-cdn.com/article/generate-a-controller-and-view-in-ruby-on-rails/Images/image001.jpg> 
</p>





[logo]: https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/Ruby_On_Rails_Logo.svg/200px-Ruby_On_Rails_Logo.svg.png "Ruby On Rails"

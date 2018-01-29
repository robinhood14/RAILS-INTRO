# Découvrez Ruby on Rails ![alt text][logo]

###### 1. La différence entre un site statique et un site dynamique
###### 2. Le MVC
###### 3. Les routes
###### 4. Les Bases de Données
###### 5. GET / POST
###### 6. Le concept de migration
###### 7. Les relations entre les models des BDD
###### 8. Les fonctions CRUD 

### Ruby On Rails , c'est quoi ? 
<hr>

Ruby On Rails, c'est un **framework** écrit en Ruby pour faire des sites/app web. 

3 grand principes : 

- Le DRY (Don't Repeat Yourself) : 
Rails encourage à ne pas écrire plusieurs fois le même code. Rendre réutilisable le code de vos applications est une bonne chose !
- Convention over configuration: 
Rails se base uniquement sur des conventions, non sur de la configuration (à l'inverse d'autres langages comme Java par exemple). Si vous respectez ces principes de convention, vous rendrez votre code maintenable et vous gagnerez en productivité.
- REST : 
c'est le meilleur design pattern pour le développement d'applications web. Il vous permet d'organiser vos applications autour de verbes HTTP standards.


### Site statique ou site dynamique ?
<hr>
 Lorsque vous tapez dans la barre d’adresse ou que vous cliquez sur un lien, vous demandez en fait à un serveur de vous afficher un document HTML qui est stocké à un endroit précis sur ce serveur. Le serveur obéit et vous renvoie ce fameux document que vous lui avez demandé. Il s'agit d'un site **statique**.


Dans un site **dynamique**, le processus est différent, le fichier HTML n’existe pas encore. Il va être généré en fonction de **paramètres** que vous allez lui envoyer.
Vous allez les lui envoyer soit de façon **consciente**, par exemple en remplissant un formulaire et en cliquant sur envoyer. 
    
###### *Ex :  un formulaire de demande de devis, vous allez donner la quantité de produits désirée, le type de produit désiré et puis le serveur va recevoir ces paramètres et va traiter la demande.*

Vous pouvez aussi le faire de façon **inconsciente**, c’est-à-dire en **cliquant** sur un lien. Ce lien a des paramètres qui se mettent dans l’url , le script a été fait pour comprendre ces paramètres,  et en fonction de ces **paramètres** il va créer un fichier HTML.


<p align="center">
    <img src="https://www.pluralsight.com/content/pluralsight/en/blog/creative-professional/sta/static-dynamic-websites-theres-difference/_jcr_content/main/hero_blog_block/image-res.img.jpg/1446605940972.jpg" target="_blank">
</p>


### Le MVC
<hr>
<p> Plutot abstrait à définir concretement, le MVC est un principe d’organisation de code basé sur la répartition suivante : <p>
    
**La vue** cette partie du code gère l'affichage.     
La vue, c’est de la **présentation**. C’est comment on veut que la donnée soit présentée à l’utilisateur. Ça peut être le code qui pond du **HTML et CSS**, ou fait configurer de jolis boutons dans une UI par exemple.    

**Le modèle** cette partie du code gère la **manipulation des données**.  
Le modèle manipule la donnée. Dans un site Web, le modèle est souvent le code qui permet de faire de requêtes à la base de données.   

**Le contrôleur** en gros , c'est tout le **reste**.     
Il fait le **lien** ente le modele et la vue et renvoie la page a l'utilisateur. L’espèce de truc machin qu’on va mettre en place pour faire marcher le programme, c’est le contrôleur.  
<p>

<p align="center">
<img src= http://csharpcorner.mindcrackerinc.netdna-cdn.com/article/generate-a-controller-and-view-in-ruby-on-rails/Images/image001.jpg> 
</p>

Parcours utilisateur :

1. L’utilisateur envoie une requête HTTP (via le navigateur) vers le server Rails
2. Le rooter la transmet au Controller via la méthode indexe
3. Le contrôleur appelle le modèle, celui-ci va récupérer les données concernant cette requete
4. Le modèle consulte la base de données
5. Le modèle retourne les données au contrôleur
6. Le contrôleur décide de la vue à afficher et va l’appeler au sein du View
7. Le code HTML de la vue est envoyé au controleur
8. Le controlleur envoie la vue à afficher au navigateur

### Les routes 
<hr>

Les routes permettent d’**interpréter les URL** et d’**orienter** vers les bonnes actions des controleurs. La configuration se trouve dans le fichier **config/routes.rb** .

La configuration par défaut se fait par la ligne :

    1-resources :photos

Il est possible d’en déclarer plusieurs de la façon suivante :

    1-resources :photos, :books, :videos

<a href="https://www.sois-net.fr/routes-ruby-on-rails/">

### Les bases de données  
<hr>

Pour stocker les données dans ton projet, tu dois utiliser une **base de données**; ça peut être MySQL, PostgreSQL, MongoDB, etc. Il est vrai que PHP est réputé pour fonctionner avec MySQL mais ce n'est pas le seul!

Ruby On Rails utilise un **ORM**, c'est en gros un **système** qui transforme les **tables** de ta base de donnée en **version orienté objet**... pour faire simple, tu apprends une nouvelle façon de manipuler ta base de donnée. 


Pour Rails, c'est **Active Record** .En utilisant Active Record, Rails va **traduire** ton code pour que les requêtes se fassent sur ta **base de donnée**. Peu importe la syntaxe de ta base de donnée, le code sera le même, du code Ruby. C'est très pratique si tu veux changer de système de DB pendant ton projet.

<p align="center">
    <img src="http://www.ennder.fr/Documents/devs/support_de_cours_rails/images/orm.jpeg">
</p>

<p>Lorsque qu'un projet est créé , Rails créé pour nous un fichier de configuration de la base de données, qui se situe dans config/database.yml. </p>

<a href="http://v-dubois.developpez.com/ruby-on-rails/introduction/" >
    
### GET / POST
<hr>

**GET** : les données transiteront par l'URL. Cette méthode est assez peu utilisée car on ne peut pas envoyer beaucoup d'informations dans l'URL.

**POST** : les données ne transiteront pas par l'URL, l'utilisateur ne les verra donc **pas passer** dans la barre d'adresse. Cette méthode permet d'**envoyer autant** de données que l'on veut, ce qui fait qu'on la privilégie le plus souvent. Néanmoins, il faudra toujours vérifier si tous les paramètres sont bien présents et valides. 
<p align="center">
    <img src="http://media.tumblr.com/tumblr_m6gb8lux6E1r731lp.png">
</p>

### Le concept de migration
<hr>
Les migrations dans Rails nous permettent de **faire évoluer** le schema de notre base de donnée facilement, sans faire de SQL. On écrit une migration et celle-ci update notre bdd.

Une migration est donc une **sous-classe** de la classe ActiveRecord::Migration. A ce titre, elle définit **deux méthodes** : une méthode « up », qui permet d'ajouter une modification à la base de données, et une méthode« down », qui permet de retirer cette modification de la base de données. 

*Anatomie d'une migration :

      class CreateContacts < ActiveRecord::Migration
        def self.up
         create_table :contacts do |t|
            t.string :name
         t.string :email

          t.timestamps
        end
       end

        def self.down
        drop_table :contacts
        end
      end
      
*Cette migration ajoute une table « contacts », possédant deux colonnes « name » et « email » de type texte. La méthode « timestamps » quant à elle, ajoute des colonnes d'informations sur les dates de mises à jour des enregistrements. Nous détaillerons tout cela un peu plus tard.*

### Les fonctions du CRUD
<hr>

Nous allons maintenant découvrir le fonctionnement du **CRUD**. Ce terme permet de désigner les **actions de bases** pour une ressource prédéfinie :

- **C**reate, permet de créer un nouvel enregistrement, POST: /{resources}
- **R**ead, permet d'afficher un ou plusieurs enregistrements, GET: /{resources} et GET: /{resources}/:id
- **U**pdate, permet de mettre à jour un enregistrement, PUT: /{resources}/:id
- **D**estroy, permet de supprimer un enregistrement, DELETE: /{resources}/:id




[logo]: https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/Ruby_On_Rails_Logo.svg/200px-Ruby_On_Rails_Logo.svg.png "Ruby On Rails"

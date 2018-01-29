# Découvrir :fire: Ruby on Rails :fire: ![alt text][logo]

1. La différence entre un site statique et un site dynamique
2. Le MVC
3. Les routes
4. Les Bases de Données
5. GET / POST
6. Le concept de migration
7. Les relations entre les models des BDD
8. Les Fonctions du CRUD


### Différence entre un site statique et un site dynamique
<hr>


- Un site statique est le type de site Web le plus basique et le plus facile à créer. Il ne nécessite aucun traitement côté serveur, uniquement côté client. Les technologies côté client sont HTML, CSS et JavaScript. En termes plus simples, il ne nécessite aucune utilisation du "back end". Un site Web statique est livré à un utilisateur exactement comme il est stocké. Cela signifie que rien sur la page ne sera modifié par l'utilisateur ou même l'administrateur du site, sauf s'il y a une refonte du site ou si l'administrateur du site va directement dans le code pour le changer. Rien n'est stocké à part les pages réelles du site. Il n'y a pas d'utilisateurs, pas de commentaires, pas de billets de blog ou d'interactivité. Aucun langage de programmation n'est requis pour créer un site statique.

<div> 


- Il existe un moyen simple de déterminer si un site est dynamique. Si vous pouvez interagir avec, c'est un site dynamique. Ainsi, la plupart des sites que vous visitez probablement sont des sites dynamiques, que ce soit Reddit, Twitter, Facebook. La façon dont vous pouvez interagir avec le site, et en cliquant simplement sur un lien dans le site ne compte pas, c'est plus comme commenter un article, créer un profil d'utilisateur ou faire une réservation. Les exemples de sites dynamiques sont les blogs, les sites de commerce électronique, les sites de calendrier ou de tâches, ou tout autre site qui doit être mis à jour fréquemment.
Pour cette raison, les sites dynamiques sont beaucoup plus compliqués et coûteux à créer. Non seulement l'hébergement Web est requis, mais des bases de données ou des serveurs doivent également être créés. Les langues utilisées pour créer des sites dynamiques sont également beaucoup plus compliquées que les langues côté client. (Ruby par exemple;))
	<a href="https://www.pluralsight.com/blog/creative-professional/static-dynamic-websites-theres-difference" target="_blank">Pluralsight</a>

</div>

<p align="center">
	<img src="https://www.pluralsight.com/content/pluralsight/en/blog/creative-professional/sta/static-dynamic-websites-theres-difference/_jcr_content/main/hero_blog_block/image-res.img.jpg/1446605940972.jpg" target="_blank">
</p>


### Le MVC
<hr>
<p>
 Modèle-vue-contrôleur ou MVC est un motif d'architecture logicielle destiné aux interfaces graphiques lancé en 1978 et très populaire pour les applications web. Le motif est composé de trois types de modules ayant trois responsabilités différentes : les modèles, les vues et les contrôleurs.<a href="https://fr.wikipedia.org/wiki/Mod%C3%A8le-vue-contr%C3%B4leur">Wikipedia</a>

**Le modèle**  contient les données à afficher. Il traite principalement les données et les interactions avec la base de données. 

**La vue** contient la présentation de l'interface graphique. Elle restitue le modèle au sein de notre interface web et permet à l’utilisateur d’interagir avec le modèle.

**Le contrôleur** fait le lien entre le modèle et la vue, il gère les requêtes des utilisateurs et détermine les traitements qui doivent être effectués pour chaque action. Il va utiliser les données du modèle, les traiter et les envoyer à la vue pour que celle-ci les affiche. C'est le cerveau.
<a href="https://openclassrooms.com/courses/apprenez-a-programmer-en-java/mieux-structurer-son-code-le-pattern-mvc">Source</a>


- Cheminement d'une requête :
1. L’utilisateur envoie une requête HTTP (via le navigateur) vers le server Rails
2. Le rooter la transmet au Controller via la méthode indexe
3. Le contrôleur appelle le modèle, celui-ci va récupérer les données concernant cette requete
4. Le modèle consulte la base de données 
5. Le modèle retourne les données au contrôleur
6. Le contrôleur décide de la vue à afficher et va l’appeler au sein du View
7. Le code HTML de la vue est envoyé au controleur 
8. Le controlleur envoie la vue à afficher au navigateur



<p align="center">
	<img src="https://user.oc-static.com/files/399001_400000/399354.png" alt="MVC" target="_blank">
</p>


### Les routes
<hr>

Les routes permettent d’interpréter les URL et d’orienter vers les bonnes actions des controlleurs.
La configuration se trouve dans le fichier config/routes.rb .
*lien: intéressant:* [Routes](https://www.sois-net.fr/routes-ruby-on-rails/)


<a href="http://guides.rubyonrails.org/routing.html">Routing avec Rails DOC</a>

<a href="https://openclassrooms.com/courses/continuez-avec-ruby-on-rails/simplifiez-la-configuration-de-vos-routes">Open Classrooms</a>


### Les Bases de Données
<hr>

Une base de données (database en anglais),
permet de stocker et de retrouver l'intégralité de données brutes ou d'informations en rapport avec un thème ou une activité ;
celles-ci peuvent être de natures différentes et plus ou moins reliées entre elles. Dans la très grande majorité des cas,
ces informations sont très structurées, et la base est localisée dans un même lieu et sur un même support.
Ce dernier est généralement informatisé.
La base de données est au centre des dispositifs informatiques de collecte, mise en forme,
stockage et utilisation d'informations. Le dispositif comporte un système de gestion de base de données (abréviation : SGBD):
un logiciel moteur qui manipule la base de données et dirige l'accès à son contenu.
De tels dispositifs — souvent appelés base de données — comportent également des logiciels applicatifs,
et un ensemble de règles relatives à l'accès et l'utilisation des informations.

<a href="https://www.tutorialspoint.com/ruby-on-rails/rails-database-setup.htm">Rails DB setup</a>


### GET / POST
<hr>


GET : les données transiteront par l'URL. Cette méthode est assez peu utilisée car on ne peut pas envoyer beaucoup d'informations dans l'URL.


POST : les données ne transiteront pas par l'URL, l'utilisateur ne les verra donc pas passer dans la barre d'adresse. Cette méthode permet d'envoyer autant de données que l'on veut, ce qui fait qu'on la privilégie le plus souvent. Néanmoins, il faudra toujours vérifier si tous les paramètres sont bien présents et valides. 

<p align="center">
	<img src="https://image.slidesharecdn.com/servletandjsp-160521134141/95/servlet-and-jsp-interview-questions-7-638.jpg?cb=1463844382">
</p>


<a href="https://openclassrooms.com/courses/concevez-votre-site-web-avec-php-et-mysql/transmettre-des-donnees-avec-les-formulaires">Open Clasrooms</a>


### Le concept de migration
<hr>

Les migrations sont des classes Ruby créés pour simplifier la création et la modification de tables dans les BDD. Dans Rails on peut faire évoluer le schema de notre base de donnée facilement, sans faire de SQL. 
On écrit une migration et celle-ci update notre BDD. Une bonne conception de la base de données passera forcément par une écriture correcte des migrations. Les migrations sont un outil puissant car elles permettent de gagner un temps fou lors de l'initialisation d'un projet Rails


Anatomie d'une migration :

	class CreateContacts <ActiveRecord::Migration
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


<p>
Cette migration ajoute une table « contacts », possédant deux colonnes « name » et « email » de type texte. La méthode « timestamps » quant à elle, ajoute des colonnes d'informations sur les dates de mises à jour des enregistrements. Nous détaillerons tout cela un peu plus tard.</p>

<a href="http://edgeguides.rubyonrails.org/active_record_migrations.html">Doc Ruby Migrations</a>

<a href="https://scotch.io/tutorials/understanding-migrations-in-rails">Rails Migrations Explained</a>


### Les relations entre les models des BDD
<hr>

Le modèle le plus courant, appelé modèle relationnel, trie les données dans des tables, que l'on appelle aussi des relations, dont chacune se compose de colonnes et de lignes. Chaque colonne contient un attribut de l'entité en question, comme le prix, le code postal ou la date de naissance. L'ensemble des attributs d'une relation est appelé domaine. La clé primaire est constituée par un attribut spécifique ou une combinaison d'attributs. On peut y faire référence dans d'autres tables : elle est alors appelée clé étrangère.
Chaque ligne, également appelée tuple, comprend des données sur une instance spécifique de l'entité en question, comme un employé en particulier.
Le modèle tient également compte des types de relations entre ces tables, notamment les relations un-à-un, un-à-plusieurs et plusieurs-à-plusieurs.
<a href="https://www.lucidchart.com/pages/fr/quest-ce-quun-mod%C3%A8le-de-base-de-donn%C3%A9es">Source</a>

<p align="center">
	<img src="https://blog.philipphauer.de/blog/2015/0514-relational-databases-strength-weaknesses-mongodb/ImpedenceMismatch-OO-Relational1.png" alt="bdd">
</p>




### Les fonctions du CRUD
<hr>



<p align="center">
	

- **C**reate, permet de créer un nouvel enregistrement, POST: /{resources}
- **R**ead, permet d'afficher un ou plusieurs enregistrements, GET: /{resources} et GET: /{resources}/:id
- **U**pdate, permet de mettre à jour un enregistrement, PUT: /{resources}/:id
- **D**estroy, permet de supprimer un enregistrement, DELETE: /{resources}/:id
</p>

#### L'acronyme CRUD se réfère à la majorité des opérations implémentées dans les bases de données relationnelles. Chaque composante de l'acronyme peut être associé à un type de requête en SQL ainsi qu'à une méthode HTTP.

Par exemple, une application carnet d'adresse dont l'élément le plus simple est un contact, doit permettre à l'utilisateur de :

- Créer des contacts
- Lire un contact (liste, zone de recherche…)
- Mettre à jour un contact
- Supprimer un contact



[logo]: https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/Ruby_On_Rails_Logo.svg/200px-Ruby_On_Rails_Logo.svg.png "Ruby On Rails"

<hr>

<p align="center">
	<img src="https://cdn-images-1.medium.com/max/1200/1*iIiiKaJKg8k9aRU8iWxCxA.jpeg" alt="MVC" target="_blank">
</p>

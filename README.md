# Découvrir Ruby on Rails ![alt text][logo]

1. La différence entre un site statique et un site dynamique
2. Le MVC
3. Les routes
4. Les Bases de Données
5. GET / POST
6. Le concept de migration
7. Les relations entre les models des BDD

<hr>
### Différence entre un site statique et un site dynamique
<hr>


Un site statique est le type de site Web le plus basique et le plus facile à créer. Il ne nécessite aucun traitement côté serveur, uniquement côté client. Les technologies côté client sont HTML, CSS et JavaScript. En termes plus simples, il ne nécessite aucune utilisation du "back end". Un site Web statique est livré à un utilisateur exactement comme il est stocké. Cela signifie que rien sur la page ne sera modifié par l'utilisateur ou même l'administrateur du site, sauf s'il y a une refonte du site ou si l'administrateur du site va directement dans le code pour le changer. Rien n'est stocké à part les pages réelles du site. Il n'y a pas d'utilisateurs, pas de commentaires, pas de billets de blog ou d'interactivité. Aucun langage de programmation n'est requis pour créer un site statique.

<div> 
<p>

Il existe un moyen simple de déterminer si un site est dynamique. Si vous pouvez interagir avec, c'est un site dynamique. Ainsi, la plupart des sites que vous visitez probablement sont des sites dynamiques, que ce soit Reddit, Twitter, Facebook. La façon dont vous pouvez interagir avec le site, et en cliquant simplement sur un lien dans le site ne compte pas, c'est plus comme commenter un article, créer un profil d'utilisateur ou faire une réservation.

Les exemples de sites dynamiques sont les blogs, les sites de commerce électronique, les sites de calendrier ou de tâches, ou tout autre site qui doit être mis à jour fréquemment.
Pour cette raison, les sites dynamiques sont beaucoup plus compliqués et coûteux à créer. Non seulement l'hébergement Web est requis, mais des bases de données ou des serveurs doivent également être créés. Les langues utilisées pour créer des sites dynamiques sont également beaucoup plus compliquées que les langues côté client. (Ruby par exemple;))
	<a href="https://www.pluralsight.com/blog/creative-professional/static-dynamic-websites-theres-difference" target="_blank">Pluralsight</a>
</p>
</div>

<p align="center">
	<img src="https://www.pluralsight.com/content/pluralsight/en/blog/creative-professional/sta/static-dynamic-websites-theres-difference/_jcr_content/main/hero_blog_block/image-res.img.jpg/1446605940972.jpg" target="_blank">
</p>

<hr>
### Le MVC
<hr>
<p>
Ce *design pattern* est une solution reconnue permettant de séparer l’affichage des informations (la vue), les actions de l’utilisateur (le contrôleur) et l’accès aux données (le modèle).

**Le modèle** est ce que l’on appelle un objet, c’est le cœur de l’application. Il traite principalement les données et les interactions avec la base de données.

**La vue** traite ce que nous voyons dans notre navigateur web, elle restitue le modèle au sein de notre interface web et permet à l’utilisateur d’interagir avec le modèle.

**Le contrôleur** fait le lien entre le modèle et la vue, il gère les requêtes des utilisateurs et détermine les traitements qui doivent être effectués pour chaque action. Il va utiliser les données du modèle, les traiter et les envoyer à la vue pour que celle-ci les affiche.
<a href="https://www.supinfo.com/articles/single/1625-mvc-presentation-patron-conception" target="_blank">Source</a>

<p>

1. L’utilisateur envoie une requête HTTP

2. Le contrôleur appelle le modèle, celui-ci va récupérer les données

3. Le modèle retourne les données au contrôleur

4. Le contrôleur décide de la vue à afficher, va l’appeler

5. Le code HTML de la vue est envoyé à l’utilisateur pour qu’il puisse naviguer normalement



<p align="center">
	<img src="https://www.elephorm.com/system/files/imagecache/thumb_full_widescreen/formations/MASTER-SYMPHONY/vignettes/le-design-pattern-mvc.jpg" alt="MVC" target="_blank">
</p>

<hr>
### Les routes
<hr>

Une route c'est une url ou unique ressource locator ex : `"/"` c'est la route qui est à la racine de notre application.

Dans le framework Rails nos routes se trouve dans `config/routes.rb` => a requette HTTP, la route/url, le controlleur et l'action ex: `GET /articles(:id) articles#index` 

Une route c' est un verbe qui représente la requette HTTP.

Dans les contrôleurs, il existe sept routes très fréquemment utilisées :

>index, create, show, update, destroy, new, edit.

On peu les ajouter manuellement dans le fichier config.rb ou  bien comme ceci : `resources :articles`

En ligne de commande on peut afficher toutes les routes disponibles dans notre application comme ceci:

`rails routes`

`GET  /articles(.:format) articles#index`

`POST  /articles(.:format) articles#create`

`GET  /articles/new(.:format) articles#new`

`GET  /articles/:id/edit(.:format) articles#edit`

`GET  /articles/:id(.:format) articles#show`

`PATCH  /articles/:id(.:format) articles#update`

`PUT  /articles/:id(.:format) articles#update`

`DELETE /articles/:id(.:format) articles#destroy`

<a href="http://guides.rubyonrails.org/routing.html">Routing avec Rails DOC</a>

<a href="https://openclassrooms.com/courses/continuez-avec-ruby-on-rails/simplifiez-la-configuration-de-vos-routes">OPC</a>

<hr>
### Les Bases de Données
<hr>

Dans le fichier `config/database.yml` on constate que Rails utilise par default sqlite3, ceci est modifiable dès l' installation avec l' option `-d` ou `--database` `mysql, oracle, postgresql, sqlite3, frontbase, ibm_db, sqlserver, jdbcmysql, jdbcsqlite3, jdbcpostgresql, jdbc`

On peut également configurer un base de donnée par environnement, development, test, production.

>Une base SQLite3 a la particularité d'être contenue dans un fichier qui porte le même nom.

```
default: &default
  adapter: sqlite3
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  timeout: 5000

development:
  <<: *default
  database: db/development.sqlite3
test:
  <<: *default
  database: db/test.sqlite3
production:
  <<: *default
  database: db/production.sqlite3
  ```

<p align="center">

  <img src="https://ruudwijnands.files.wordpress.com/2014/03/database_yml_-_testproject_-____rubymineprojects_testproject_.png" alt="database" targer="_blank">
  </p>

<a href="https://www.tutorialspoint.com/ruby-on-rails/rails-database-setup.htm">Rails DB setup</a>

<hr>
### GET / POST
<hr>


GET : les données transiteront par l'URL. Cette méthode est assez peu utilisée car on ne peut pas envoyer beaucoup d'informations dans l'URL.

>NEVER TRUST USER INPUT

POST : les données ne transiteront pas par l'URL, l'utilisateur ne les verra donc pas passer dans la barre d'adresse. Cette méthode permet d'envoyer autant de données que l'on veut, ce qui fait qu'on la privilégie le plus souvent. Néanmoins, il faudra toujours vérifier si tous les paramètres sont bien présents et valides. 

<p align="center">
	<img src="http://www.java8s.com/img/get.PNG" alt="get-vs-post">
</p>


<a href="https://openclassrooms.com/courses/concevez-votre-site-web-avec-php-et-mysql/transmettre-des-donnees-avec-les-formulaires">OPC</a>

<hr>
### Le concept de migration
<hr>

Les migrations dans Rails nous permettent de faire évoluer le schema de notre base de donnée facilement, sans faire de SQL. 
On écrit une migration et celle-ci update notre bdd.

<p align="center">
	<img src="https://leanpub.com/site_images/rails3dot0-astudentmanual/db-cheatsheet.png" alt="db-cheatsheet" traget="_blank">
</p>

<a href="http://edgeguides.rubyonrails.org/active_record_migrations.html">Doc Ruby Migrations</a>

<a href="https://scotch.io/tutorials/understanding-migrations-in-rails">Rails Migrations Explained</a>

<hr>
### Les relations entre les models des BDD
<hr>

Le modèle le plus courant, appelé modèle relationnel, trie les données dans des tables, que l'on appelle aussi des relations, dont chacune se compose de colonnes et de lignes. Chaque colonne contient un attribut de l'entité en question, comme le prix, le code postal ou la date de naissance. L'ensemble des attributs d'une relation est appelé domaine. La clé primaire est constituée par un attribut spécifique ou une combinaison d'attributs. On peut y faire référence dans d'autres tables : elle est alors appelée clé étrangère.
Chaque ligne, également appelée tuple, comprend des données sur une instance spécifique de l'entité en question, comme un employé en particulier.
Le modèle tient également compte des types de relations entre ces tables, notamment les relations un-à-un, un-à-plusieurs et plusieurs-à-plusieurs.
<a href="https://www.lucidchart.com/pages/fr/quest-ce-quun-mod%C3%A8le-de-base-de-donn%C3%A9es">Source</a>

<p align="center">
	<img src="https://blog.philipphauer.de/blog/2015/0514-relational-databases-strength-weaknesses-mongodb/ImpedenceMismatch-OO-Relational1.png" alt="bdd">
</p>


<a href="https://openclassrooms.com/courses/faites-une-base-de-donnees-avec-uml/comprendre-les-cles-primaires">OPC Clefs Primaires</a>

<a href="https://openclassrooms.com/courses/faites-une-base-de-donnees-avec-uml/mettez-en-oeuvre-les-differents-types-de-relations-a-laide-des-cles-etrangeres#">OPC Suite</a>


[logo]: https://upload.wikimedia.org/wikipedia/commons/thumb/6/62/Ruby_On_Rails_Logo.svg/200px-Ruby_On_Rails_Logo.svg.png "Ruby On Rails"


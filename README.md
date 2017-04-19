# Exercice technque OuiCar

Pour résoudre cet exercice, veuillez : 

- Forker ce repository 
- Répondre aux questions une à une __sur des branche distinctes__. La branche N démarre bien entendu du code de la branche N-1.
- Envoyer votre repository ainsi que les explications pour lancer votre serveur à théo@ouicar.fr
- N'oubliez pas de nous dire combien de temps vous avez pris à faire cet exercice et comment vous l'avez trouvé. Cela n'est pas pris en compte dans l'évaluation mais nous servira pour l'améliorer :-)

Dans cet exercice vous devrez reproduire le coeur du système le location de OuiCar : le dépôt de véhicules ainsi que leur réservation. Tout est ici implicite, à vous d'utiliser les technologies qu'il convient afin de répondre à l'exercice. La seule contrainte est le language de programmation qui devra être PHP, et la base de données devra être de type relationnelle.

Il n'est pas nécessaire d'implémenter la logique d'authentification, on considèrera que l'API permet d'exécuter des actions pour n'importe quel utilisateur.


BONUS POINTS* (si vous avez trouvé ça trop facile) :
- Documentation de l'API (swagger ou autre...)
- Tests unitaires - TDD
- Déployer votre serveur en ligne (heroku, aws...)

MEGA BONUS POINT* (si vraiment vous vous ennuyez beaucoup) : 
- Gérer l'authentification et les droits d'accès aux ressources - attention si vous attaquez cette partie soyez sûr de vous !

\*Les Bonus Points sont très appréciés mais ne sont pas obligatoires. Attention aussi à ne pas être contre productif et bacler ces bonus points, si vous décidez de les réaliser il faudra les implémenter jusqu'au bout et dans les règles de l'art.

Question n°1 :

Écrire une API pour créer une voiture sur OuiCar. Une voiture a les paramètres et contraintes listés ci-dessous : 

- mileage : kilométrage (1 = entre 0 et 50 000 km, 2 = entre 50K et 100K, 3 = entre 100K et 150K, 4 = + de 150K)
- price_day_1 : prix en centimes du premier jour et du second jour
- price_day_3 : prix en centimes du jour 3 au jour 6 inclus
- price_day_7 : prix en centimes à partir du 7ème jour de location

Question n°2 :

Écrire une API pour signifier qu'une voiture est indisponible et qu'un locataire ne peut pas la louer.

- Les indisponibilités sont des périodes d'une demi-journée, ex: 1 = matin (de 0h00 à 11h59), 2 = aprem (de 12h00 à 23h59) pour une date donnée
- Une indisponibilité s'applique à une voiture donnée

Question n°3 :

Écrire une API pour réserver un véhicule à la location. Une location s'effectue entre deux demi journées sur une voiture donnée pour un locataire inscrit dans notre base utilisateur, et il faut bien sûr que la voiture soit disponible à la location sur cette période.
Une voiture est indisponible si le propriétaire l'a signifié via l'API de la question n°2, ou si elle a déjà été réservée sur ces créneaux.

Question n°4 :

Voilà 3 ans que notre service de réservation existe et que notre magnifique API est utilisée par de nombreux terminaux front (l'app ios, l'app android, le web, le webmobile, ...)
Nous souhaitons changer le mileage qui n'est pas assez précis (valeur discrète pour le moment) et permettre à nos propriétaires de mettre le kilométrage exact de leur véhicule.
Mettre à jour en conséquence l'API

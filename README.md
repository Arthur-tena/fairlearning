# Lecture d'article - Fairlearning
Ce repository a été crée par 
- Arthur TENA ; arthur.tena@etu.umontpellier.fr
- Jeanne MANNEQUIN ; jeanne.mannequin@etu.umontpellier.fr
- Jeanne VIVIER ; jeanne.vivier@etu.umontpellier.fr
- Mario LAPI ; mario.lapi@etu.umontpellier.fr

On y traite ici la notion de fairlearning avec un exemple appliqué au jeu de donnée COMPAS.
La notion d'équité peut être définit de plusieurs façon différentes, nous allons donc souligné dans notre étude 2 définitions ;la parité démographique  et l'égalité des chances.

Le jeu de donnéee COMPAS (Correctional Offender Management Profiling for
Alternative Sanctions), vient du logiciel du même nom conçu pour estimer les risques de récidive des criminels, est
accepté pour usage juridique par la cour suprême du Wisconsin.

L'étude de ce jeu de donnée a montré le biais racial de ce logiciel. Nous nous concentrerons plutôt sur le biais de genre dans notre étude.


Ce repository contient un notebook montrant notre étude sur le biais de genre dans le data set COMPAS.

Dans une première partie nous verrons les 2 définitions sur le jeu de donnée "brut" (c'est à dire sans débiaisage) puis nous ferons la même chose mais avec le jeu de donnée débiaisé avec la méthode de pré-processing appelée "Optimized pre-processing" que nous allons définir ensuite.

# Optimzed pre processing :
Dans "Optimized Pre-Processing for Discrimination Prevention", les auteurs proposent une optimisation convexe visant à apprendre une transformation des données avec trois objectifs : contrôler la discrimination, limiter la distorsion dans les échantillons individuels, et préserver l'utilité. 
Pour cela, l'article traite d'un algorithme de pré-traitement organisé. C'est une méthode consistant à ajuster les données avant de les utiliser dans des modèles d'apprentissage automatique. Les 3 objectifs mentionnés sont les suivant   : 

•**Contrôle de la discrimination** : Il est important dans un premier temps de réduire la dépendance entre les variables causant la discrimination (comme le genre ou la race) et la réponse (comme les années de prison).

•**Limitation de la distorsion individuelle** : Dans un second temps, l’algorithme s’assure que chaque donnée individuelle ne soit pas trop transformé afin que les informations originales sur chaque individu ne soient pas trop déformées.
•**Préservation de l'utilité des données** : Enfin, il faut maintenir les propriétés statistiques des données transformées proches des données d'origine pour que les modèles prédictifs puissent rester performants.

Ces 3 critères définissent le côté optimisation de la méthode.

Dans l'article, les auteurs testent leur algorithme sur deux jeux de données, dont celui de COMPAS. Les résultats montrent que l'application de leur méthode de transformation des données a permis d'obtenir des classifications plus équitables par rapport aux ensembles de données d'origine. La réduction de la discrimination a cependant entraîné une légère perte de précision, due aux restrictions imposées par la transformation aléatoire des données. Malgré cette pénalité en termes de précision, leur méthode reste compétitive par rapport à d'autres approches présentes dans la littérature. Un des avantages clés de leur approche est la possibilité d'exercer un contrôle explicite sur l'équité individuelle, tout en gérant des variables protégées multivariées et non binaires.

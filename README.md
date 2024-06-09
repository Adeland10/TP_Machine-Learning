# TP_Machine-Learning

PS : Voir mes codes et graphiques sur mon fichier google collab

PARTIE 1 : Analyse Exploratoire des Données (EDA)
-----------------------------------------------------------------------------------------------------------------------------
1.1 Vue d'ensemble des données :

Questions :

1) Quelles sont les différentes colonnes du jeu de données ?
D'après df.head(), il y a 27 colonnes de jeu de données : ID,gender,age,height(cm),weight(kg),waist(cm),eyesight(left),eyesight(right),hearing(left),hearing(right),systolic,relaxation,fasting blood sugar,Cholesterol,triglyceride,HDL,LDL,hemoglobin,Urine protein,serum creatinine,AST,ALT,Gtp,oral,dental caries,tartar,smoking

2) Combien y a-t-il d'entrées dans le jeu de données ?
D'après df.describe(), il y a 55702 entrées dans le jeu de données.

3) Le jeu de données contient-il des valeures nulles ? Si oui combien ?
Oui, il y en a 12.

-----------------------------------------------------------------------------------------------------------------------------
1.2 Statistiques descriptives :

Questions :
1) Quelle est la moyenne d'âge, de taille et de poids des fumeurs ?
fumeurs = df[df['smoking'] == 1]

if not fumeurs.empty:
  print(fumeurs[["age","height(cm)","weight(kg)"]].mean())

else:
  print("nope")
Pour les fumeurs, on   a age            43.560813
                         height(cm)    169.435401
                         weight(kg)     70.959376

2) Y a-t-il des motifs ou des valeurs aberrantes notables dans les données ? (Un age 200 ans par exemple)
Oui il y en a plein, âge 170 ans ??????????

3) Quelle est l'écart type de l'hémoglobine ?
import math

list=df['hemoglobin']

mean = list.mean()
var = sum((l - mean) ** 2 for l in list) / len(list)
st_dev = math.sqrt(var)

print(st_dev)

=1.5644617074469365

-----------------------------------------------------------------------------------------------------------------------------
1.3 Distribution de la donnée :

Question
1) Combien y a-il de fumeur vs non-fumeur ? Le résultat doit être présenté sous forme de "pie chart"
  not smocking 63,3% et smocking 36,7%

2) Combien d'hommes? sont fumeurs ? Combien de femmes ? Afficher un histogramme
homme smocking = 19598
femme smocking = 859
   
3) Quelle est la moyenne d'age des hommes fumeurs ?
Moyenne d'age homes fumeurs = 43.437005664132265

fumeurs = df[df['smoking'] == 1]
male_fumeurs = fumeurs[fumeurs["gender"] == 'M']
male_fumeurs['age'].mean()

-----------------------------------------------------------------------------------------------------------------------------
1.4 Analyse de corrélation :
Calculer et visualiser la matrice de corrélation, le but étant d'étudier la corrélation des variables entre elles. 

Questions :

1) Quel problème rencontrez-vous ?
J'obtiens une erreur : "ValueError: could not convert string to float: 'F'" sûrement due au fait que j'ai des valeurs abberantes et des variables catégorielles dans mon fichier.

Passez à la partie 2 et revenez aux questions suivante plus tard.

2)Quelles variables sont les plus fortement corrélées entre elles ?
pas réuissi à faire la matrice de corrélation
3)Comment la variable cible (fumeur) est-elle corrélée avec les autres variables ? Donnez le top 3
pas réussi à faire la matrice de corrélation

----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------
Partie 2 : Data pre-processing
----------------------------------------------------------------------------------------------------------------------------
2.1 Gestion des Valeurs Manquantes :
(voir mes codes pour application de la méthode)

Questions :
1) Quelle méthode avez-vous choisie pour gérer les valeurs manquantes et pourquoi ?
J'ai choisi d'utiliser l'imputation par la moyenne pour les variables numériques et par la mode pour les variables catégorielles. Parce que c'est une méthode simple qui permet de conserver toutes les données sans en supprimer, ce qui est utile si les valeurs manquantes sont rares.

2) Comment cette méthode impacte-t-elle les données ?
L'avantage c'est qu'on garde toutes les données, donc on ne perd aucune information. Mais, elle peut introduire un biais si les valeurs manquantes ne sont pas distribuées de manière aléatoire et peut réduire la variabilité des données, affectant ainsi certains types d'analyses statistiques.
----------------------------------------------------------------------------------------------------------------------------
2.2 Encodage des catégories
Questions :
1) Quel autre traitement de la donnée pourriez-vous faire pour optimiser l'entraînement ?
Normalisation/Standardisation des variables numériques : permet de mettre toutes les variables sur la même échelle, bien pour améliorer les performances des algorithmes de machine learning.

----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------
Partie 3 
----------------------------------------------------------------------------------------------------------------------------


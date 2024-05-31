# TP_Machine-Learning

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
Calculer et visualiser la matrice de corrélation, le but étant d'étudier la corrélation des variables entre elles. Questions :

Quel problème rencontrez-vous ?

Passez à la partie 2 et revenez aux questions suivante plus tard.

Quelles variables sont les plus fortement corrélées entre elles ?

Comment la variable cible (fumeur) est-elle corrélée avec les autres variables ? Donnez le top 3


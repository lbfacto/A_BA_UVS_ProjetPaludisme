﻿# projetPalu-A-BA

#**Rapport Projet**

Abdoulaye BA

Master 2 Big Data

Université Virtuelle du senagal

module cas industriel

**I.INTRODUCTION**

Ce rapport decrit l'analyse des données de paludismeulisatant utilisant un algorithme

de support vetor machine  que nous allons expliquer dans le rapport dans la partie modelisation et resultat  pour l'apprentissage automatique. sur nos données

cette ensemble de données provient d'une localite du pays et contenant des informations et  des valeurs de mesures differentes,  comme le ratio le G6PD etc...

Les objectifs de cette analyse sont le developpement d'un model predictif pour predire les cas de paludismes ent utilisant les variables numeriques et continues de ce dataset

telles que le ratio le G6PD et les autres variables numeriques. Ensuite apres une analyse faite sur les données il en suit le developpment de deux  programmes bases sur le web pour faire l'analyses la visualisation et le generation de rapport  sur les doonees uploder au format html pour plus de visualisation interactif une mailleur comprehension des donnees  et un autre programme pour faire  la prediction suite a un entrainement qui est fait sur les donnees. Suivant notre model de machine learning serialiser sur un model.pkl qui va servir pour renseigner au programme sur qui a le paludisme ou/non. voir code.

## II. Methodologies

Les donnes recues ont ete dabord nettoyer et preparer dans un premeir temps  avec un classeur excel ouj'ai mis une condition SI ratio > 2 positif sinon negatif sur le classeur pour mesurer le nombre le nombre les cas cas positiif/negatif  afin de choissr les caracterisques les plus pertinentes pour notre model avant de faire un model.

# II.1 Choix des variables

Dans la cette section pour choisir les variables pertinents j'ai fais fait un rpofiling des donnees sur le programme autml pour voir les variables et leur importances dans le dataset parapport aux autres variables qui nous permetaient de faire un bon model. Pour choisr les varaiables pour notre model.  on a fait l'analyse et determiner quelles etaient les plus perninentes, ils s'est trouves que tous less variables numeriques avaient des correlation forte entre eux. Cest de la que le choix des ces variables est venue. ce chois est fait grace au programme AUTOML mis en place pour ca voir code et rapport Html generer.

# II.2 Modelisation

Dans ce travail j'ai utilise un svm (Support Vector Machine (SVM) est un type d'algorithme de classification supervisée qui peut également être utilisé pour la régression. Il est basé sur l'idée de trouver un sous-espace de caractéristiques qui sépare de manière optimale les différentes classes de données.

Il utilise des fonctions de noyau pour transformer les données en un espace de caractéristiques de dimension plus élevée où il est plus facile de séparer les classes. Les fonctions de noyau les plus couramment utilisées sont la fonction linéaire, la fonction polynômiale et la fonction gaussienne (RBF).

SVM est souvent utilisé pour les problèmes de classification à deux classes, mais il peut également être étendu à des problèmes à plusieurs classes en utilisant des techniques d'extension telles que One-vs-All et One-vs-One.

Il est également utilisé pour les problèmes de classification non linéaires, où il est utilisé pour séparer les données qui ne peuvent pas être séparées de manière linéaire en utilisant des fonctions de noyau.

Il a deux principaux avantages: Il est efficace pour les données de grande dimension et il est efficace pour les données qui contiennent un grand nombre de variables par rapport aux observations.) pour entrainer notre model .

Le d'un svm est le resultat d'un entrainement sur plusieur model en amont ceci pour vaoir le resultat de ces models et faire une compareaison entre ces model suivant leurs accurances(voir app.py  application de modelisration) pour pouvoir faire un choix sur le model le plus performant pour nos données "

-Les données ont été divisées en ensemble d'entraînement et ensemble de test, avec un ratio 80/20 respectivement. avec les modules de sklearn
-Un SVM a été entraîné en utilisant l'ensemble d'entraînement, avec un kernel lineaire avec le creation d'une nouvellle colonne resulltat en fonction du ratio et binariser entre 0 et 1 pour les postifs au paludisme et les negatifs au paludisme. cette colonne nous a servis de target pour la l'entrainement et la prediction dans notre procecus..

# II.3 Resultats

-Les performances du modèle ont été évaluées en utilisant l'ensemble de test,

des mesures telles que la precision du rappel et de l'auc-roc voir partie metrique pour les resulats suivant:

Accurance : 0.97766 ce qui veut dire que l'exactitude du model entrainé est de 99.3% ce qui montre qui'il est capable de predire avec une grande precision les cas de paludismes

Precision : 0.9212 ce qui montre que le model est capables de predire les cas de paludismes a 92.12%

Recall : 0.9811 ce qui veur dire que le model a reussi a detecter correctement 98% des cas de palusdismes

AUC-ROC : 0.9998

Apres un entrainement de plusieur model depuis notre apllication qui sont les suivants  on  a trouve que le svm avait la plus bonne accurance de 0.97766   une grande precision sur les autres models voir metrics.json

voir aplliacation pour plus de details sont dans le script appUVS.py et palusvm.py.

voir application pour plus de detail sur les resultats obtuenus.

> Pour la visualistaion voir overview html 

# III Conclusion 

Le model svm utilsé pour cette tache a eu une boone precison une boone accurance et predit à 97% les classes pour determiner le cas de paludismes ou non. En fin ce model a été implementé sur une applicatiojn de prediction our les variables imposées par le model pour faire une prediction  avec un ensembles de taches et un base de données qui va recuperees tous les predictions sur une tables malades et une tables medecins qui enregistres les medeicns qui ont fait cettes taches voir dossier projet  grace au framework de streamlit, et qui sont deployes sur streamlit cloud.

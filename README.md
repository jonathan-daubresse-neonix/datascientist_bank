# Description du projet

La description du projet permet de fournir tout un ensemble d'information par rapport au contexte et au secteur cible. Certaines informations essentielles, comme les contraintes du projet ou encore les objectifs à atteindre, y sont définies.

Dans un contexte concurrentiel, une banque cherche à fidéliser ses clients en leur proposant des services adaptés. Pour cela, elle s'intéresse à savoir quels sont les clients qui sont susceptibles de résilier tout ou une partie de leurs produits bancaires.

Pour cela, la banque dispose d'un historique sur plusieurs années de clients qui ont soient résilié leurs produits (ils ont churn), soient restés clients de la banque. Un jeu de données a été extrait depuis la base de données principale contenant l'ensemble des clients (actuels et anciens) de la banque, accompagnés d'informations supplémentaires (nombre de produits bancaires, localisation, âge).

L'objectif est de déterminer si un client de la banque va résilier son contrat ou non à l'avenir en utilisant ses informations financières et personnelles connues de la banque. Cette problématique de score d'attrition (ou churn en anglais) est une problématique de classification binaire que l'entreprise cherche à résoudre en utilisant ses propres données.

Contraintes
En pratique, détecter si un client va résilier son contrat est une tâche difficile, car les comportements de ce dernier ne peuvent pas être entièrement prévisibles. Néanmoins, les offres promotionnelles sont intéressantes uniquement pour les clients qui vont potentiellement résilier, car ceux qui n'en n'ont pas l'intention conserveraient leur contrat, même en l'absence d'offre promotionnelle.

La métrique principale visée est donc l'AUC, calculée à partir de la courbe ROC, car elle permet de prendre en compte les faux positifs.

Le modèle de Machine Learning retenu devra présenter un score AUC supérieur à 72%. Il est demandé de vérifier la stabilité de ce résultat en effectuant une validation croisée 
k
k-Fold, dont on accompagnera d'un écart-type.

Description des données
La base comprend 10,000 clients répartis sur trois pays (France, Allemagne et Espagne). Elle contient les colonnes suivantes.

CustomerId : identifiant unique du client.
Surname : nom du client.
CreditScore : score de crédit entre 100 et 1000, calculé par la banque. Ce score indique la solvabilité du client dans le cas d'un emprunt : plus le score est élevé, plus le client est considéré comme solvable.
Geography : pays de résidence du client.
Genger : sexe du client.
Age : âge du client.
Tenure : indice d'ancienneté du compte bancaire entre 1 et 10. Plus le nombre est élevé, plus le compte bancaire du client est ancien.
Balance : solde du compte courant au moment de l'extraction des données depuis la base, exprimés en centaines de centimes (60125,00 indique 601,25€ sur le compte bancaire).
NumOfProducts : le nombre de produits bancaires auquel le client a souscrit (assurance vie, comptes épargne, etc).
HasCrCard : indique si le client possède une carte de crédit.
IsActiveMember : indice calculé par la banque si le client effectue des débits et crédits réguliers sur son compte courant.
EstimatedSalary : salaire annuel estimé du client.
Exited : indique si le client a résilié son contrat avec la banque.

# initialisation
python3.12 -m venv mon_env
source mon_env/bin/activate
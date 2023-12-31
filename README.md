# SearchVinted

## Description du projet

SearchVinted est un outil innovant conçu pour les passionnés de shopping sur Vinted, la plateforme de vente en ligne de vêtements et d'articles de mode d'occasion. Ce projet vise à améliorer l'expérience de recherche d'articles en permettant aux utilisateurs de filtrer et de trouver les objets qui correspondent exactement à leurs besoins, d'ajouter de nouveau filtres lorsque les filtres standard de l'application ne suffisent pas.

Cas d'utilisation:
- Filtrer les produits pour un pays donné pour limiter l'impact du transport sur l'environnement
- Trier les produits par pays
- Vérifier quelles sont les marques les plus vendues pour un pays donné.
- ...

## Mise en place
1. Cloner le projet:
- git clone git@github.com:Antoine-ValentinCharpentier/SearchVinted.git

2. Se déplacer dans le répertoire:
- cd SearchVinted

3. Initialiser l'environnement virtuel:
- python -m venv .venv
- .venv\Scripts\activate OU source .venv/bin/activate
- pip install -r requirements.txt

4. Installer Google Chrome
5. Télécharger le Chrome Driver adéquat
- Regarder la version de chrome que vous disposez en cliquant sur les ... en haut de chrome > Aide > A propos
- Aller sur le site https://chromedriver.chromium.org/downloads et télécharger la version du driver adéquat
- Extraire l'exécutable du zip
- placer l'exécutable à la racine du projet, c'est-à-dire au même niveau que scrapper.ipynb

6. Executer le notebook scrapper.ipynb

## Remarques
- À noter que le projet a été réalisé les 14 et 15 septembre 2023. Comme le projet utilise des méthodes de scraping, il est possible qu'il ne fonctionne plus à l'avenir si Vinted décide de modifier les noms des classes ou la structure de leur page web. Ainsi, si le programme ne fonctionne pas, il faut d'abord vérifier que vous disposez de la bonne version du Chrome Driver, puis vérifier les noms des classes.

- Le point précédent s'explique par le choix d'utiliser le scraping plutôt que d'effectuer des requêtes HTTP. Cela permet d'ajouter de la signification au contenu recherché par l'utilisateur sur le site. Par exemple, il est plus intuitif de sélectionner un élément dans un menu déroulant (comme le type de vêtement) que de devoir saisir un numéro (ID) correspondant à ce type de vêtement. Il en va de même pour les tailles, les combinaisons de tailles, les matériaux, etc., ce qui serait difficile à comprendre pour l'utilisateur.

- À quoi correspondent les fichiers générés lors de l'exécution ?
    - ``config.txt`` : Il s'agit du fichier qui permet de stocker les filtres par défaut de Vinted afin de ne pas avoir à les ressaisir la prochaine fois. Vinted sauvegarde les filtres dans l'URL via des Query Params. Ainsi, le fichier comporte uniquement l'URL vers la page avec les filtres par défaut configurés.
    - ``output`` : Il s'agit d'un dossier permettant de stocker les résultats des précédentes recherches. Ainsi, la prochaine fois, l'algorithme ne visitera pas à nouveau les produits déjà consultés et ne parcourra que les nouveaux produits. Cela permet donc de gagner un temps considérable.
        1. ``output/location.json`` : Il stocke les URL des produits visités, triés par localisation.


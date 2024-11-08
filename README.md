# Application Météo

Cette application web permet aux utilisateurs de rechercher la météo en temps réel d'une ville en saisissant simplement son nom en français dans la barre de recherche.

- Pour voir et tester l'application : [application-meteo](https://applicationmeteo.netlify.app/)



## Aperçu

<img src="src/assets/images/screenshot.png" alt="Aperçu de l'application" width="400" />



## Fonctionnalités

- Recherche de la météo : Entrez le nom d'une ville (en français) dans le champ de recherche.

- Informations météo : Obtenez la température actuelle de la ville et une description des conditions météorologiques, comme "ensoleillé", "nuageux", "pluvieux", etc...



## Prérequis 

- [Node JS](https://nodejs.org). 

- Vérifier l'installation avec `node -v`



## Technologies utilisées

- Vue.js 2 : Framework JavaScript pour construire l'interface utilisateur

- Axios : Utilisé pour faire des requêtes HTTP à l'API météo

- API météopenweathermap : API tierce pour récupérer les données météo en temps réel [openweathermap](https://openweathermap.org). Créer un compte gratuit pour avoir une clé d'API et une URL 



## Installation et utilisation

### 1. Cloner le dépôt 
```
git clone https://github.com/Melissa-code/projet_meteo.git
cd projet_meteo 
```

### 2. installer les dépendances
```
npm install
```

### 3. Configurer la clé API

- Créer un fichier .env.local à la racine du projet qui ne sera pas commité (cf. fichier .gitignore)

- Ajouter la clé API avec VUE_APP_ : 
```
VUE_APP_API_KEY='cleApiExemple453323454'
```

- Récupérer la variable d'environnement avec process.env.:
```
process.env.VUE_APP_API_KEY,
```

- Stoper et redémarrer le serveur 
```
ctrl + C 
npm run serve
```



## Deployer l'application 

- Aller sur le site [Netlify](https://app.netlify.com)

- Créer un compte/se connecter

- Importer un projet existant

- Choisir "Déployer avec GitHub" 

- Configurer "the Netlify app on GitHub"

- Sélectionner le repository "projet_meteo"

- Choisir un nom de site ("check availability")

- Ajouter une variable d'environnement (key/value & sélectionner "Deploy without sensitive variables")

- Deployer 

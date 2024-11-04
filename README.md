# projet_meteo

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


## Variables d'environnement 

- Create a .env file :

variables d'environnement doivent commencer par VUE_APP_ pour être reconnues par l'application
```
VUE_APP_API_KEY=''
```

- Add the .env in the .gitignore file 


- Then in the component :
```
api_code: process.env.VUE_APP_API_KEY,
```

- Stop & run the server 

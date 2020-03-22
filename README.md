# Configuración de plantilla base

### 1. Instalación de npm


### 2. Intalación de Parcel

Instalación de Parcel como paquete global ya que es una herramienta que se utilizará mucho.
Si se instalase dentro del proyecto habría que usar npx.


### 3. Configuración de Git

Incluir en el fichero .gitignore los ficheros de los que no queremos hacer seguimiento. Para ello, se ha utilizado la página *gitignore.io* para las tecnologías *Node*, *VisualStudio Code* y *Git*.


### 4. Creación del árbol de directorios y ficheros

```
.
├── build
├── dist
│   ├── css.967bad95.css
│   ├── css.967bad95.css.map
│   ├── css.967bad95.js
│   ├── css.967bad95.js.map
│   ├── index.html
│   ├── js.00a46daa.js
│   └── js.00a46daa.js.map
├── LICENSE
├── package.json
├── README.md
└── src
    ├── assets
    ├── css
    │   └── index.css
    ├── index.html
    └── js
        └── index.js

6 directories, 13 files
```


### 5. Inicilizar npm 
    ``` npm init -y ```
    Añadir scripts a *package.json*:

```
"scripts": {
    "build": "parcel build src/index.html",
    "dev": "parcel src/index.html",
    "deploy": "parcel build src/index.thml --public-url /plantilla-dsi/ -d build"
},
 ```


### 6. Ejecutar Parcel
    ``` parcel src/index.html ```
    El servidor corre el el puerto 1234 de la máquina local.


### 7. Linters
```
npm install -D eslint
npx eslint --init
```

Cambiar configuración del fichero *.eslintrc.json*
```
"rules": {
    "semi": ["error", "always"]
}
```

Para ejecutar ESLint: ``` npx eslint src ```
Para corregir automáticamente los errores: ``` npx eslint src --fix ```


### 8. Prettier

```
npm install -D prettier
npm install -D eslint-config-prettier eslint-plugin-prettier
```

La última línea añade prettier como un plugin de eslint para evitar conflictos entre ambos.


### 9. Desplegar en GitHub Pages

```
npm install -D gh-pages
parcel build src/index.html  --public-url https://github.com/PaulaExposito/plantilla-dsi -d build
npx gh-pages -d build  # npm run pages
```

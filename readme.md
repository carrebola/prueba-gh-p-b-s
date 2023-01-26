# Proyecto Front End con Vanilla
1. Creamos carpeta
2. npm create vite .
3. npm i
4. npm run dev
5. Modificamos index.html para verificar
6. npm run build para crear dist
7. Creamos vite.config.js para indicar en 'base' que sustituya '/' por './' para poder publicar en github pages
8. Creamos repositorio publico y subimos a github
9. npm i gh-pages
10. añadimos a package.json la orden  "deploy": "gh-pages -d dist"
11. npm run deploy. Si todo ha ido bien veremos publicada nuestra rama con la carpeta dist
12. Configuramos nuestra pagina para que sea visible y veremos resultado en el enlace que nos da github
13. Instalamos bootstrap npm i --save bootstrap @popperjs/core
14. Instalamos sass npm i --save-dev sass
15. Construimos nuestro scafolding src con carpeta scss
16. Creamos archivo styles.scss y copiamos

 @import "~bootstrap/scss/bootstrap";

17. Modificamos vite.config.js con

export default {
   
  root: path.resolve(__dirname, 'src'),
  resolve: {
    alias: {
      '~bootstrap': path.resolve(__dirname, 'node_modules/bootstrap'),
    }
  },
  server: {
    port: 8080,
    hot: true
  },
  plugins: [
    defineConfig({
        base: './',
    })
  ]
}
18. En el archivo main.js importamos styles.scss y bootstrap

// Import our custom CSS
import '../scss/styles.scss'

// Import all of Bootstrap's JS
import * as bootstrap from 'bootstrap'

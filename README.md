# ToDo App
TodoApp es aplicativo de gestión de tareas. Consume la API de JSONPlaceholder.

[Demo](https://todo-app-vue-v2.herokuapp.com/ "Demo")

[![Screenshot ToDo App](https://todo-app-vue-v2.herokuapp.com/app-screenshot.png "Screenshot ToDo App")](https://todo-app-vue-v2.herokuapp.com/ "Screenshot ToDo App")

## Instalación para desarrollo
```shell
# Clonar el repositorio
git clone https://github.com/dmpb/todo-app-vue.git

# Ejecutar
npm run dev
```
## Instalación para despliegue
Para desplegar el proyecto se debe seguir los pasos de viter. [Enlace de despliegue con Viter](https://vitejs.dev/guide/static-deploy.html "Enlace de despliegue con Viter")
### Heroku
Hay algunos inconvenientes con el despliegue con Heroku. Por ello, se recomienda seguir estos pasos de despliegue:

1. Install [Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli "Heroku CLI").
1. Configuración del proyecto

	```shell
	# Crear un nuevo app con un específico nombre
	heroku apps:create example

	# set buildpack for static sites
	heroku buildpacks:set heroku/nodejs -a <your-app-name>

	heroku buildpacks:add https://github.com/heroku/heroku-buildpack-static.git -a <your-app-name>
	```
1. Deploy your site:

	```shell
	# publish site
	git push heroku main

	# opens a browser to view the Dashboard version of Heroku CI
	heroku open
	```

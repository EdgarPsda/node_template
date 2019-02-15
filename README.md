# MVC Node Clean Proyect
Este es un proyecto MVC limpio para nodeJs con:   
* Express
* Pug
* Sequelize
* Nodemon
* Nvm 
* Npm.   

Con este proyecto evitas la instalación de las dependencias cada que vas a comenzar un proyecto en nodeJs.  

# Instalación

A continuación te describo los pasos a seguir para crear éste proyecto.

1. Instalar nvm (Node Version Manager) con el siguiente comando:   
    `curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.34.0/install.sh | bash`   

2. instalar nodeJS, la ultima version LTS.   
    `nvm install 10.15.1`   

3. Instalar express js generator.   
    `npm install express-generator -g`

4. Crear el proyecto.   
    `express --view=pug [nombre del proyecto]`

5. Entrar a la carpeta del proyecto creado.   
    `cd [nombre del proyecto]`

6. Instalar npm.   
    `npm install`

7. Crear la carpeta para los controladores.   
    `mkdir controllers`

8. Instalar nodemon para recargar el servidor automáticamente.   
    `npm install nodemon --save-dev`

9. Configurar el archivo package.json para nodemon, debe quedar de la siguiente forma   
    `"start": "if [[ $NODE_ENV == 'production']]; then node ./bin/www; else nodemon ./bin/www; fi"`

10. Instalar sequelize.   
    `npm install sequelize`   
    `npm install sequelize --save`   
    `npm install sequelize-cli -g`   

11. Crear el archivo .sequelizerc para la configuración de sequilize.   
    `touch .sequelizerc`   

12. Dentro del archivo .sequelizerc quedara con la siguiente configuración para la base de datos:   
    ```
    const path = require('path');

	    module.exports = {
		    'config': path.resolve('config', 'config.js'),
		    'models-path': path.resolve('', 'models'),
		    'seeders-path': path.resolve('', 'seeders'),
		    'migrations-path': path.resolve('', 'migrations')
	    }
    ```   

13. Inicializar sequelize, este comando creara algunas carpetas para el buen uso del MVC.   
    `sequelize init`

14. El archivo config.js que se encuentra dentro de la carpeta config, se ingresará la configuración de la base de datos, quedando de la siguiente forma.   
    ```
        module.exports = {
    "development": {
    "username": "usuario",
    "password": ' password',
    "database": "db_name",
    "host": "127.0.0.1",
    "dialect": "dbms",
    "port" : 5432
    },
    "test": {
    "username": "root",
    "password": null,
    "database": "database_test",
    "host": "127.0.0.1",
    "dialect": "mysql"
    },
    "production": {
    "username": "root",
    "password": null,
    "database": "database_production",
    "host": "127.0.0.1",
    "dialect": "mysql"
     }
    }
    ```   

15. Crear la carpeta para las migraciones.   
    `mkdir migrations`   

Espero te sirva este template para un proyecto en NodeJs, cualquier aporte es bien recibido.




# Documentation for Project 3 (MERN)

## BACKEND CONFIGURATION

`sudo apt update`

`sudo apt upgrade`

`curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -`

![Node location](./images/location-nodejs.png)

`sudo apt-get install -y nodejs`

Node version:

![Node version](./images/node-version.png)

Npm version:

![Npm version](./images/npm-version.png)

`mkdir Todo`

`cd Todo`

`npm init`

![Npm init](./images/npm-init.png)

## INSTALL EXPRESSJS

`npm install express`

![install express](./images/install-express.png)

`touch index.js`

![index](./images/create-index.png)

`npm install dotenv`

![install dotenv](./images/install-dotenv.png)

`nano index.js`

![config index](./images/config-index.png)

`node index.js`

![Node index](./images/port-5000.png)

Add new inbound rule:

![Add inbound rules](./images/adding-inbound-rule.png)

`mkdir routes`

`cd routes`
![routes dir](./images/routes-dir.png)

`touch api.js`

`nano api.js`

![config api](./images/config-api.png)

## MODELS

Change directory into Todo folder.

`npm install mongoose`

![install mongoose](./images/install-mongoose.png)

`mkdir models`

`cd models`

`touch todo.js`

![models dir](./images/models-dir.png)

`nano todo.js`

![configure todo.js](./images/config-todo-js.png)

Update api.js in routes folder to use new model:

`nano api.js`

![update api.js](./images/update-api.png)




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

## MONGODB DATABASE

Set up an account with mLab and allow access to the new MongoDB from anywhere.

`touch .env`

`nano .env`

Add the connection string to access the database in it, just as below:

![Add to .env](./images/connect-clusterMERN.png)

Update index.js with this code:

<!-- const express = require('express');
const bodyParser = require('body-parser');
const mongoose = require('mongoose');
const routes = require('./routes/api');
const path = require('path');
require('dotenv').config();

const app = express();

const port = process.env.PORT || 5000;

//connect to the database
mongoose.connect(process.env.DB, { useNewUrlParser: true, useUnifiedTopology: true })
.then(() => console.log(`Database connected successfully`))
.catch(err => console.log(err));

//since mongoose promise is depreciated, we overide it with node's promise
mongoose.Promise = global.Promise;

app.use((req, res, next) => {
res.header("Access-Control-Allow-Origin", "\*");
res.header("Access-Control-Allow-Headers", "Origin, X-Requested-With, Content-Type, Accept");
next();
});

app.use(bodyParser.json());

app.use('/api', routes);

app.use((err, req, res, next) => {
console.log(err);
next();
});

app.listen(port, () => {
console.log(`Server running on port ${port}`)
});` -->

`node index.js` to start server

Got this error:

![error](./images/error2.png)

Reason for this is due to .env being placed in the Todo dir instead of ~ dir.

Install Postman to test API endpoints

POST request:

![post](./images/POST.png)

GET request:

![get](./images/GET.png)

DELETE request:

![delete](./images/DELETE.png)

<!-- I passed the id into the url to get the DELETE request. Please let me know if this is the correct/optimal way to do so. -->

## FRONTEND CREATION

Create react app in Todo dir:

`npx create-react-app client`

![react app](./images/create-react-app.png)

`npm install concurrently --save-dev`

![install concurrently](./images/install-concurrently.png)

`npm install nodemon --save-dev`

![install nodemon](./images/install-nodemon.png)

Update package.json file with code below in Todo dir:

<!-- "scripts": {
"start": "node index.js",
"start-watch": "nodemon index.js",
"dev": "concurrently \"npm run start-watch\" \"cd client && npm start\""
}, -->

Configure proxy:

Go to client dir and update package.json:

![proxy](./images/adding-proxy.png)

Also add inbound rule:

![inbound rule 3000](./images/port-3000.png)

`npm run dev`

It worked however I did get an error while running the app:

![error](./images/locolhost3000.png)

Create components:

`cd client`

`cd`

`mkdir components`

`cd components`

![components](./images/components.png)

`touch Input.js ListTodo.js Todo.js`

`nano Input.js`

Copy and paste the following:

<!-- import React, { Component } from 'react';
import axios from 'axios';

class Input extends Component {

state = {
action: ""
}

addTodo = () => {
const task = {action: this.state.action}

    if(task.action && task.action.length > 0){
      axios.post('/api/todos', task)
        .then(res => {
          if(res.data){
            this.props.getTodos();
            this.setState({action: ""})
          }
        })
        .catch(err => console.log(err))
    }else {
      console.log('input field required')
    }

}

handleChange = (e) => {
this.setState({
action: e.target.value
})
}

render() {
let { action } = this.state;
return (
<div>
<input type="text" onChange={this.handleChange} value={action} />
<button onClick={this.addTodo}>add todo</button>
</div>
)
}
}

export default Input -->

Install Axios:

`npm install axios`

![install axios](./images/install-axios.png)




# Thunk

## About

1...2...Thunk!

Thunk is a game that inspires creativity, through quick thinking and clever limitations. It is a multi-player, multi-screen game built to experiment with Socket.IO and Node.js. This project is a fork of [@Minious/fibbage-tribute](https://github.com/Minious/fibbage-tribute).

## Usage

1. If testing locally, start application from root of repository `npm start`
1. If testing locally, connect to localhost:3000, if using in production, connect to [thunk.fun](https://thunk.fun)
1. Click Create, to start a new game
1. Click Join, to enter an existing game, then input the data we need to steal from you

### Gameplay
1. On the large screen (the game Host), a sentence with a missing word will appear.
2. On each players' devices, a text field appears.
3. The players must provide a ploy which has to be credible.
4. One each players send their ploys, the game host and the players' devices display the ploys and the real answer to the sentence.
5. The player who taps the correct answer gets 10 points and if a player choose a ploy, the player who provided it gets 5 points.
6. The player with the most points at the end of the game wins!

## System Requirements

Requires [nodejs/npm installation](https://nodejs.org/en/), mysql Server and mysql workbench.
Note: This project uses the jQuery CDN on the client.

## Installation

Clone this repo into your preferred directory. 

    git clone https://github.com/project-dali/thunk-2

Navigate to that directory in the terminal 
    
    cd thunk-2 

then install this project's node depencies

    npm install

If you would like to test locally, you will need a local [mysql installation](https://dev.mysql.com/downloads/mysql/) and a mysql server/interface such as [mysql Workbench](https://www.mysql.com/products/workbench/). 

Setup a login/password on your local sql. Create a new file in the Thunk project repository called `db-secret.js` and add the following information, replacing `{username}` and `{password}` with the login credentials you just created (by default the username will be root, unless you specified otherwise):

```js
const dbCredentials = {
    host: "localhost",
    user: "{username}",
    password: "{password}",
    database: "thunk"
}

module.exports.dbCredentials = dbCredentials;
```

To import the database schema and data, run this [sql import script](https://b7s9.com/quick-drop/export-7.sql) in mysql workbench. You are now ready to begin local development.

## Test

To test on local, navigate to the root directory of the app and run:

    npm start

The app will be available on [localhost:3000](http://localhost:3000).

## Deploy 

Log in to the remote server as the shared non-root user, navigate to ~/thunk/

```shell
$ git pull
$ git checkout master
$ pm2 restart thunk
```

If any new npm packages were added,
```shell
$ npm install
$ pm2 restart thunk
```

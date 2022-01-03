# Express Generator

This is a guide for getting up and running with a "skeleton" website created with express-generator.

## Create express application

Enter following command into CLI to create application using pug as view template language:

```bash
npx express-generator --view=pug <projectName>
```

cd into new project directory and install dependencies:

```bash
cd <projectName>
npm install
```

## Enable server restart on save

Use nodemon to automatically update server when file changes are made. (Still requires a browser page refresh):

```bash
npm install --save-dev nodemon
```

Add the following scripts to your package.json file:

_ALERT: Be sure to substitute your actual project name into the serverstart script._

```json
"scripts": {
  "start": "node ./bin/www",
  "devstart": "nodemon ./bin/www",
  "serverstart": "DEBUG=<projectName>:* npm run devstart"
}
```

To start the server:

```bash
npm run serverstart
```

## To view server in browser

Navigate to [http://localhost:3000/](http://localhost:3000/)

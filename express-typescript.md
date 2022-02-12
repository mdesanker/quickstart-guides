# Express Server with TypeScript

In terminal, create folder, navigate into it, and create package.json

```bash
mkdir file-name && npm init
```

Install dependencies

```bash
npm i express
npm i -D typescript ts-node @types/express @types/node nodemon
```

Create tsconfig.json in root folder

```bash
npx tsc --init
```

Add start script in package.json

```json
"scripts": {
  "start": "nodemon index.ts"
}
```

Create index.ts file and get started

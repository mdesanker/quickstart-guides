# Express Server with TypeScript

### Initialize

In terminal, create folder, navigate into it, and create package.json

```bash
mkdir file-name && npm init
```

### .gitignore

Create .gitignore file with `touch .gitignore` and add the following:

```json
node_modules
.env
```

### Essential dependencies

Install dependencies

```bash
npm i express
npm i -D typescript ts-node @types/express @types/node nodemon
```

### TypeScript config file

Create tsconfig.json in root folder

```bash
npx tsc --init
```

Replace tsconfig.json with the following

```json
{
  "compilerOptions": {
    "target": "es2016",
    "module": "commonjs",
    "typeRoots": ["@types", "./node_modules/@types"],
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true,
    "strict": true,
    "skipLibCheck": true
  }
}
```

### Running server

Add start script in package.json

```json
"scripts": {
  "start": "nodemon app.ts"
}
```

Create `app.ts` file and get started

### Additional dependencies:

```bash
npm i dotenv cors compression helmet express-validator
npm i -D @types/cors @types/compression jest @types/jest ts-jest supertest @types/supertest
```

### Extend express req object with declaration merging

Add following folders and declaration file to project root directory

```bash
|- /@types
  |- /express
    |- index.d.ts
```

Add the following to `index.d.ts`

```typescript
import express from "express";
import { Express } from "express-serve-static-core";

declare global {
  namespace Express {
    interface Request {
      user: {
        id?: string;
      };
    }
  }
}
```

### Setup testing with supertest and jest

Add test script to `package.json` and add route to test file

```json
"scripts": {
  "test": "NODE_ENV=test jest <INSERT ROUTE TO TEST FILE HERE> --testTimeout=10000 --detectOpenHandles --forceExit"
}
```

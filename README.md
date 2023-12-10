## Steps to use Node with TypeScript with Nodemon

1. Install TypeScript and Node types, as a development dependency.

   ```bash
   npm i -D typescript @types/node

2. Initialize the TypeScript configuration file.

   ```bash
   npx tsc --init --outDir dist/ --rootDir src

3. Configure Nodemon and Node-TS.

    ```bash
    npm install -D ts-node nodemon

4. Create Nodemon configuration file - nodemon.json.

    ```bash
    {
        "watch": ["src"],
        "ext": ".ts,.js",
        "ignore": [],
        "exec": "npx ts-node ./src/app.ts"
    }

5. Create script to run in development in package.json.

    ```bash
    "dev": "nodemon"
    "dev": "npx nodemon" // In case you don´t want to install nodemon

6. Install rimraf (Tool that works similar to rm -f) delete directory.

    ```bash
    npm install -D rimraf

7. Create scripts in the package.json to build and launch into production.

    ```bash
    "build": "rimraf ./dist && tsc",
    "start": "npm run build && node dist/app.js"

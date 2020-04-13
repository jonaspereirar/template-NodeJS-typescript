yarn init -y
yarn add express
yarn add typescript
yarn tsc --init  (tsconfig) "outDir": "./dist", //vai gerar a bild "rootDir": "./src"
src/server.ts
yarn tsc //vai criar a pasta dist/ e gerar o ficheiro js

in server.ts
import express from 'express'

const app = express()

app.get('/', (request, response) => {
  return response.json({ message: 'Hello World' })
})

app.listen(3333, () => {
  console.log(' Server started on port 3333!')
})

rodar yarn tsc para converter o código em javascript e só depois
node dist/server.js

  "scripts": {
    "build": "tsc"
  rodar yarn build // mas demora bastante e apagamos a pasta dist/
  ** instalamos 
  **yarn add ts-node-dev -D ** mais rápido que o nodemon, babel, webpack, sucrase
    "scripts": {
    "build": "tsc",
    "dev:server": "ts-node-dev src/server.ts"
  },
  **yarn dev:server // O ts-node-dev  faz o papel do nodemon e do tsc em converter para js
  ** Incluir --transpileOnly vai impedir(desabilitar) que o ts-node-dev verifique erros no código e vai torrna mais rápido em apenas converter, e apenas o vs code é quem vai verificar o código, ou seja: "dev:server": "dev:server": 
  "ts-node-dev --transpileOnly src/server.ts"

  ** Incluir --ignore-watch node_modules  para ignorar a pasta node_modules e ainda ficar mais rápido, ou seja:
      "dev:server": "ts-node-dev --transpileOnly --ignore-watch node_modules src/server.ts"
teste e remova --transpileOnly --ignore-watch node_modules para verificar velocidade
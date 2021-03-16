# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Deployment

This section has moved here: [https://facebook.github.io/create-react-app/docs/deployment](https://facebook.github.io/create-react-app/docs/deployment)

### `npm run build` fails to minify

This section has moved here: [https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify](https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify)

--------------


01. Criar repositório Github.
02. Clonar repo para desktop.
03. Criar pasta Backend
04. Em Front:
    Criar projeto com "create-react-app <nomeprj> --use-npm" (verificar doc) ou ultimo sts ok: npx create-react-app <nomeprj>/ <frontend> --use-npm
    Console: npm start
05. Em Back:
    npm init -y
    Criar .gitignore
        Atribuir /node_modules
    Opcional:
        npm i --save json-server@0.13.0 -E
        db.json // em backend ou api
        package.json "scripts" > "start": "json-server --watch db.json --port 3080"
        npm start
06. Rotas: 
    App.jsx
        import { BrowserRouter } from "react-router-dom";
        import Routes from './Routes'
        export default props =>
            <BrowserRouter>
                <div className="app">
                    <Routes />
                </div>
            </BrowserRouter>
    Routes.jsx
        import {Switch, Route, Redirect} from  'react-router'
        export default props => 
        <Switch>
            <Route exact path='/' component={Home} />
            <Route path='/contato' component={Contato}/>
            <Redirect from='*' to='/' />       
        </Switch>
    Demais componentes
    import { Link } from 'react-router-dom';
    <Link to="/destino"/>
    
07. Instalação de dependencias:
    npm install --save <tech> ou npm install <tech>
    em frontend > package.json
        "axios": "^0.21.1",
        "bootstrap": "4.1.1",
        "font-awesome": "4.7.0",
        "jquery": "^3.4.1",
        "reactstrap": "^8.4.1"
    cd frontend > npm i
        NPM install <...>
        Para criar API pode ser usado fetch, axios, express.
        Para ter segurança com dados e usar o process.env.<...> usar dotenv
    
    App.jsx
        import 'bootstrap/dist/css/bootstrap.min.css'
        import 'font-awesome/css/font-awesome.min.css'
    
08. Deploy
    Packagejson "scripts" > "build": "react-scripts build"
    cd nomeprj:
        npm run build
        npm install -g serve
        serve -s build
09. Netfily        
        
### Nova estrutura
Folders structure
general
|
--frontend
    |
    --src
       |
       --imgs
       --components
         |
         --templates > partes da tela .jsx e .css
         --home 
       --main > App.js (declaracao de dependencias) / App.css / Routes
--backend
    |
    -- db.json
                            node_modules/ 

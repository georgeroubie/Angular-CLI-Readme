# Angular CLI Readme
> This is the readme file that [Pobuca](https://www.pobuca.com) uses in every Angular CLI Project.


# General information
This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version X.X.X


## Installation
 1. Install git from [here](https://git-scm.com/download/win)
 2. Install node js from [here](https://nodejs.org/en/download)
 3. Run as admin globally:   
    + `npm install npm@latest -g`  
	+ `npm install @angular/cli@8.2.0 -g` 
    + `npm install rimraf -g` 
	+ `npm cache clean -f` 
 4. Install Visual Studio Code from [here](https://code.visualstudio.com) 
 5. Install these Visual Studio Code extensions:   
    + `Project Snippets`
	+ `#region folding for VS Code`
	+ `EditorConfig for VS Code`
	+ `stylelint`
	+ `Azure Account`
	+ `Azure App Service`
 6. Run as admin in the folder that you want to contain the project `git clone project-url`
 7. Open the generated folder with Visual Studio Code (File > Open Folder...)
 8. Open terminal and run `npm install`


## Run
 1. Open Project with Visual Studio Code (File > Open Folder...)
 2. Open terminal and split the terminal in two `Ctrl + \`
 3. On the left side run `npm start` and automatically the browser will navigate to `http://localhost:YYY1`
 4. On the right side run `npm run test` to execute the unit tests and automatically the browser will navigate to `http://localhost:YYY2`


## Publish to Production
The running url is: https://angularwebapp.azurewebsites.net  
 1. Open `master` branch
 2. Merge `development` branch to `master`
 3. Open terminal and run `npm run build`, this action will generate a dist folder
 4. Open `Azure: APP SERVICE` Visual Studio Code Extension
 5. Got to `Web Services` > `angularwebapp`, right click to `angularwebapp` and choose `Deploy to Web App...`
 6. On File Explorer choose the dist folder
 7. Delete local dist folder


## Publish to Development
The running url is: https://angularwebapp-dev.azurewebsites.net  
 1. Open `development` branch
 2. Open terminal and run `npm run build`, this action will generate a dist folder
 3. Open Azure: APP SERVICE Visual Studio Code Extension
 4. Got to `Web Services` > `angularwebapp > Deployment Slots > dev`, right click to `dev` and choose `Deploy to Slot...`
 5. On File Explorer choose the dist folder
 6. Delete local dist folder


## Format code
 1. Install the `EditorConfig for VS Code` extension and reload Visual Studio Code
 2. Use these keys inside a file: `Shift` + `Alt` + `F`


## Use comment region
 1. Install the `#region folding for VS Code` extension and reload Visual Studio Code
 2. Select the code you want
 3. Use these keys: `Ctrl` + `M` + `R`


## When package.json is changed
 1. Open Project with Visual Studio Code (File > Open Folder...)
 2. Open terminal and run `rimraf node_modules dist package-lock.json`  
 3. Open terminal and run `npm cache clean -f`  
 4. Open terminal and run `npm install`  


## Angular CLI Commands
 1. When you run an angular cli command you should use the flag `-d` for testing the result.  
 2. When you are sure that the result of the command is correct, then remove the `-d` flag.

### Create Module
 1. Run: `ng g m name --routing -d`  
 2. Import the module in the `AppModule`
 3. Check for routing issues with other modules
 4. Import the `SharedModule` in the created module and remove any used module import, e.g. CommonModule

### Create Component in Module
 1. Run: `ng g c moduleName/name --skipTests=true --inlineStyle=true -d`    
    If you don't want the component to have it's own folder add the flag `--flat`
 2. Add the component, in the routes object of the file: `src/moduleName/moduleName-routing.ts`

### Create Component in Main Module
 1. Run: `ng g c main/components/name --skipTests=true --inlineStyle=true -d`

### Create Feature Module
 1. Run: `ng g m main/modules/name --routing -d`  
 2. Lazyload the module in the `src/main/main-routing.module.ts` like this:  
    `{ path: 'name', loadChildren: () => import('./modules/name/name.module').then(m => m.NameModule) }`
 3. Import the `SharedModule` in the created module and remove any used module import, e.g. CommonModule

### Create Component in a Feature Module
 1. Run: `ng g c main/modules/featureModuleName/name --skipTests=true --inlineStyle=true -d`    
    If you don't want the component to have it's own folder add the flag `--flat`
 2. Add the component, in the routes object of the file: `src/main/modules/featureModuleName/featureModuleName-routing.ts`

### Create Service
 1. Run: `ng g s core/services/name --skipTests=true -d`  
 2. Remove the `providedIn: 'root'` from the service
 2. Add the service in the providers array of the CoreModule

### Create Utility
 1. Run: `ng g s core/utilities/nameUtility --skipTests=true -d`  
 2. Delete the word Service from the class name, but not from the file name.
 3. Remove the `providedIn: 'root'` from the utility
 4. Add the utility in the providers array of the CoreModule

### Create Factory
 1. Run: `ng g s core/factories/nameFactory --skipTests=true -d`
 2. Delete the word Service from the class name, but not from the file name.
 3. Remove the `providedIn: 'root'` from the factory
 4. Add the factory in the providers array of the CoreModule

### Create Guard
 1. Run: `ng g g core/guards/name --skipTests=true -d`
 2. Remove the `providedIn: 'root'` from the guard
 3. Add the guard in the providers array of the CoreModule

### Create Shared Component
 1. Run `ng g c shared/components/name --skipTests=true --export=true --inlineStyle=true -d`
 2. Add the component shortcut in the `.vscode/snippets/html.json` in order to easily use it everywhere

### Create Shared Pipe
 1. Run: `ng g p shared/pipes/name --skipTests=true --export=true -d`  

### Create a Class that every module can use
 1. Run: `ng g cl shared/classes/name -d`  

### Create an Interface that every module can use
 1. Run: `ng g i shared/interfaces/name -d`  
 2. Add the letter `I` in the beginning of the interface name not in the file name.

### Create an Enum  that every module can use
 1. Run: `ng g e shared/enums/name -d`  

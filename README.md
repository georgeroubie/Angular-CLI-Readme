# Angular CLI Readme
This is the readme file that I created for the Frond-End Dept. of [Pobuca](https://pobuca.com), in order to use it in every Angular CLI Project.


# General information
This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version X.X.X


## Installation
  1. Install git from [here](https://git-scm.com/download/win)
  2. Install node js from [here](https://nodejs.org/en/download)
  3. Run as admin globally `npm install npm@latest -g`  
  4. Run as admin globally `npm install @angular/cli@X.X.X -g`  
  5. Run as admin globally `npm install rimraf -g`  
  6. Run as admin globally `npm cache clean -f` 
  7. Install Visual Studio Code from [here](https://code.visualstudio.com) 
  8. Install the `Project Snippets` extension and reload Visual Studio Code
  9. Install the `#region folding for VS Code` extension and reload Visual Studio Code
 10. Install the `EditorConfig for VS Code` extension and reload Visual Studio Code
 11. Run as admin in the folder that you want to contain the project `git clone project-url`
 12. Open the generated folder with Visual Studio Code (File > Open Folder...)
 13. Open terminal and run `npm install`


## Run
 1. Open Project with Visual Studio Code (File > Open Folder...)
 2. Open terminal and split the terminal in two `Ctrl + \`
 3. On the left side run `npm start` and automatically the browser will navigate to `http://localhost:YYY1`
 4. On the right side run `npm run test` to execute the unit tests and automatically the browser will navigate to `http://localhost:YYY2`


## Publish
 1. Open Project with Visual Studio Code (File > Open Folder...)
 2. Git Sync  
 3. Open terminal and run `npm run test`
 4. Open terminal and run `npm run build`   
 5. Write here the next step based on the project


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


## When Angular CLI needs update
To update Angular CLI to a new version, you must update both the global package and your project's local package.  

### Global package:  
 1. Run as admin globally `npm uninstall -g @angular/cli`  
 2. Run as admin globally `npm cache clean -f`  
 3. Run as admin globally `npm install -g @angular/cli@latest`  

### Local project package:  
 1. Open Project with Visual Studio Code (File > Open Folder...)
 2. Open terminal and run `rimraf node_modules dist package-lock.json`     
 3. Open terminal and run `npm install --save-dev @angular/cli@latest`  
 4. Open terminal and run `npm install`  


## Angular CLI Commands
 1. When you run an angular cli command you should use the flag `-d` for testing the result.  
 2. When you are sure that the result of the command is correct, then remove the `-d` flag.

### Create Component in Main Module
 1. Run: `ng g c main/components/name --skipTests=true --inlineStyle=true -d`

### Create Feature Module
 1. Run: `ng g m main/modules/name --routing -d`  
 2. Lazyload the module in the `src/main/main-routing.module.ts` like this: `{ path: 'name', loadChildren: './modules/name/name.module#NameModule' }`
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

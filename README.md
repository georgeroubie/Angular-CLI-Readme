# Angular CLI Readme
This is the readme file that I created for the Product Development Team of [Pobuca](https://pobuca.com), in order to use it in every Angular CLI Project.


# General information
This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version X.X.X


## Installation
  1. Install git from [here](https://git-scm.com/download/win)
  2. Install node js from [here](https://nodejs.org/en/download)
  3. Run as admin globaly `npm install npm@latest -g`  
  4. Run as admin globaly `npm install @angular/cli@X.X.X -g`  
  5. Run as admin globaly `npm install rimraf -g`  
  6. Run as admin globaly `npm cache clean -f` 
  7. Install Visual Studio Code from [here](https://code.visualstudio.com) 
  8. Install the `Project Snippets` extension and reload Visual Studio Code
  9. Run as admin in the folder that you want to contain the project `git clone project-url`
 10. Open the generated folder with Visual Studio Code (File > Open Folder...)
 11. Open terminal and run `npm install`


## Run
 1. Open Project with Visual Studio Code (File > Open Folder...)
 2. Open terminal and split the terminal in two `Ctrl + \`
 3. On the left side run `npm start` and automatically the browser will navigate to `http://localhost:YYY1`
 4. On the right side run `npm run test` to execute the unit tests and automatically the browser will navigate to `http://localhost:YYY2`


## See the source map files
 1. Open Project with Visual Studio Code (File > Open Folder...)
 2. Open terminal and run `ng build -sm` to build and adding source map files
 3. View the source map files with this command: `source-map-explorer dist/name.js`
 4. When you are finished do not commit anything just delete the dist folder


## When package.json is changed
 1. Open Project with Visual Studio Code (File > Open Folder...)
 2. Open terminal and run `rimraf node_modules dist package-lock.json`  
 3. Open terminal and run `npm cache clean -f`  
 4. Open terminal and run `npm install`  


## When Angular CLI needs update
To update Angular CLI to a new version, you must update both the global package and your project's local package.  

### Global package:  
 1. Run as admin globaly `npm uninstall -g @angular/cli`  
 2. Run as admin globaly `npm cache clean -f`  
 3. Run as admin globaly `npm install -g @angular/cli@latest`  

### Local project package:  
 1. Open Project with Visual Studio Code (File > Open Folder...)
 2. Open terminal and run `rimraf node_modules dist package-lock.json`     
 3. Open terminal and run `npm install --save-dev @angular/cli@latest`  
 4. Open terminal and run `npm install`  


## Angular CLI Commands
 1. When you run an angular cli command you should use the flag `-d` for testing the result.  
 2. When you are sure that the result of the command is correct, then remove the `-d` flag.

### Create Module
`ng g m name -d`  
If you want the module to have routing add the flag `--routing`

### Create Component
`ng g c folderOfModule/name --skipTests=false -d`  
If you don't want the component to have it's own folder add the flag `--flat`   
If you don't want the component to have a scss file add the flag `--inlineStyle=true`  
If the module that you want create the component, is the SharedModule, don't forget to add the flag `--export=true`  

### Create Service
`ng g s core/providers/services/name --skipTests=false -d`  

### Create Guard
`ng g g core/providers/guards/name --skipTests=false -d`  

### Create Factory
`ng g s core/providers/factories/nameFactory --skipTests=false -d`  
You have to delete the word Service from the class name, but not from the file name.

### Create Utility
`ng g s core/providers/utilities/nameUtility --skipTests=false -d`  
You have to delete the word Service from the class name, but not from the file name.

### Create Pipe
`ng g p common/pipes/name --skipTests=false --export=true -d`  

### Create Interface
`ng g i core/interfaces/name -d`  

### Create Class
`ng g cl core/classes/name -d`  

### Create Enum
`ng g e core/enums/name -d`  

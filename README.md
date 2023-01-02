# Lecture - 2 Assignment

### What is `npm`?

- npm is a package manager which allows us to install and use reusable code which are called packages.

- npm stands for "Node.js Package Manager". Although the developer behind it, trolls the userbase by generating random full names for npm which can be viewed by visiting npmjs' home page and seeing the top left corener.

- npm is useful because we can just install a dependency for our project, specify how we would like it to be updated (Wether we just want bug fixes, minor updates which are backwards compatible or major updates which may not be backwards compatible)

- before npm, we used to use script tag to load external resources through CDN. But because of npm, we can install all the dependencies in the server which would be faster.

- npm has 3 backbones
	- npm registry: This holds all the npm packages. When we do `npm install <package>`, we fetch that package from the registry.
	- npm CLI: This allows us a CLI interface to interact with npm repository.
	- The website: This allows us to search and find packages.

- Also, last but not the least, npm is WORLD's LARGEST SOFTWARE REGISTRY. 

### What is Parcel/Webpack? Why do we need it?

- Parcel and Webpack are different types of Module Bundlers.

- Module bundlers allow us to bundle all our code into a single file. All different javascript files gets merged into a single js file, similarly all css gets merged into a single css file and so on. 

- Module bundlers also take care of loading assets and can also optimize assets such as images.

- Module bundlers also provide us with additional functionalities like Hot Module Replacement, Live Server, Developer Mode, Watch Mode, Tree Shaking, Minification, etc.

- Webpack is a very powerful tool but at the same time, it can be quite frustating honestly. It does not do anything out of the box, and we have to configure it to make it work. BUT, having to configure it ourselves mean that we get full control over our build process and we can add and remove the features we want. This can be done by adding "Plugins" for features and "Loaders" for managing different types of files.

- "Parcel is a beast" - Akshay Saini 2023. And, Akshay was correct. Parcel gives us same things as webpack but it requires 0 configuration. We just have to provide an entry point, and Parcel will figure out rest by itself. Also, Parcel uses caching which makes the consecutive builds after the first build pretty fast. 

### What is `.parcel-cache`?

- `.parcel-cache` is the folder which stores cache files which make consecutive builds after the first build faster.

- This is enabled by default in Parcel. If we want to use caching in Webpack, we have to do some additional configuration.

### What is `npx`? 

- `npx` is a "Package Runner". 

- It helps to execute any package from npm registry without even installing that package.

### What is difference between `dependencies` and `devDependencies`?

- `dependencies` are the packages which are required for our app to work. They can be installed using `--save` or` -S`

- `devDependencies` are the packages which are required only during development of the app by the developers. They can be installed using `--save-dev` flag or `-D`.

### What is tree shaking?

- Tree Shaking is a concept used in module bundlers which allow us to only include the code that we are using in the build. 

- This help us to make our app smaller in size and also reduces the javascript which needs to be processed and hence makes our app faster.

### What is Hot Module Replacement?

- Hot Module Replacement is a concept which allows us to only update a particular part of the mmodule which was updated instead of the entire page. 

- This makes the build process faster, as we don't update all the unupdated code again.

- This is different from Live Server or Watch Mode because HMR updates part of code, while live server gives us a server which we can use to run our app and Watch Mode gives us automatic build on saving.

### List down your favourite 5 superpowers of Parcel and describe any 3 of them.

- Zero Configuration: The most important superpower of Parcel is that it does all the heavy lifting for us and we have to spend zero time configuring it.

- Out of the box support for common module bundling features: We get HMR, Caching, Development Server, Output Management etc, Minification etc already out of the box.

- Rest features are common for other module bundlers too but here's description of some of them:
	- HMR: This allows us to only build the code we have changed.
	- Cache: This allows us to lessen the build time by caching after first build.
	- Tree Shaking: This gets rid of unused code from our app.
	- Code Splitting: This allows us to split our modules such that we only build the required stuff. For example, we can seperate all out dependencies and our custom code so that we don't have to always build the dependencies.

### What is `.gitignore` ? What should we add and not add into it?

- `.gitignore` is a file used to tell git which files or folders we don't wan't to be tracked by git.

- A rule of thumb is to only add those files/folders which can be automatically installed/built by the server. Example: `node_modules`, `.parcel-cache`.

### What is the difference between `package.json` and `package.lock.json`?

- `package.json`: 
	-  contains information about our npm package. It contains all our dependencies and dev dependencies and also things like name of the package, author, description etc.

	- `name` and `version` are required fields in `package.json`.

	- automaticaly added when initializing npm.
- `package.lock.json`: 
	- is used to track the exact version of the dependencies which are installed currently in the server. 

	-  contains the dependency tree/graph which is helpful to reproduce the exact project as built by the developer.

	- automatically added when installing any dependency.

### Why should i not modify `package.lock.json` ?

- Modifying `package.lock.json` or any other code which is there for helping the package is not a good idea. This may cause the package to break or even the entire app.

### What is `node_modules` ? Is it a good idea to push it to git?

- It contains all out external packages, both dev and normal dependencies.

- It is not a good idea to track it with git because it can get huge and also, anyone can install the `node_modules` folder by running npm install. To share an npm package, we just need the `package.json` and `package.lock.json`.

### What is `dist` folder? 

- Whatever output the module bundler gives, is stored in the dist folder by default.

### What is `browserlists`?

- It is a package which helps us to make out code backwards compatible with older browsers.

### Read about ^ and ~ in dependencies naming conventions.

- These are conventions used to specifiy which updates we would like to be automatically downloaded.

- These are almost similar to the convention used in bash/zsh to access file names.

- ^ (caret) : This symbol is used to specify a version range that is compatible with the latest minor version. For example, if the latest version of a package is 1.2.3, specifying a version range of ^1.2.3 will allow you to install any version of the package that starts with 1.2, such as 1.2.4, 1.2.5, etc.

- ~ (tilde) : This symbol is used to specify a version range that is compatible with the latest patch version. For example, if the latest version of a package is 1.2.3, specifying a version range of ~1.2.3 will allow you to install any version of the package that starts with 1.2.3, such as 1.2.3, 1.2.4, etc.

- \> (greater than) : This symbol is used to specify a version range that is greater than a certain version. For example, specifying a version range of >1.2.3 will allow you to install any version of the package that is greater than 1.2.3, such as 1.2.4, 1.3.0, etc.

- < (less than) : This symbol is used to specify a version range that is less than a certain version. For example, specifying a version range of <1.2.3 will allow you to install any version of the package that is less than 1.2.3, such as 1.1.0, 1.0.0, etc.

- \* (asterisk) : This symbol is used to specify that any version of the package is allowed.

### What are the various script types?

- Empty string, not specified : This means "classic script".

- `module` : They represent javascript modules. The `charset` and `defer` attribute have no effect on these.

- `importmap` : This represent that the body of script element is an import map. This is a JSON object that developers use to control how the browsers resolves module specifiers when importing JavaScript modules.

- Any other value : Treated as a data block. For this, a valid MIME type should be used that is not a javascript MIME type. In this case, all other attributes will be ignored including the `src` attribute.

- MIME Type : It stands for Multipurpose Internet Mail Extension. This is a way for identifying files on the internet. It contains of two parts: "type" and "subtype". Examples of type are text, image, audio etc and subtype are plain for text, jpeg for image, mpeg for audio. etc.

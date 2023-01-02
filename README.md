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



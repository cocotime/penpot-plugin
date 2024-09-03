# Minimal Plugin Template

This is a minimal Penpot plugin template.

## Pre-requisites

- Node.js and npm ([Download](https://nodejs.org/en/download/package-manager)).
- Git ([Download](https://git-scm.com/downloads)).
- Visual Studio Code ([Download](https://code.visualstudio.com/download)) or similar.
- Basic HTML, CSS and javascript knowledge.

## Folders and files

The plugin code is inside the `/src` folder, where you can find the main files like `index.html`, `main.css` and `main.js`. These files are provided as examples and can be freely modified to suit your needs.

### What is typescript?

TypeScript is like JavaScript with extra rules. These rules help you catch mistakes early, before you run your code. It makes your code more reliable and easier to manage, especially in big projects.

We're using TypeScript to make working with the Penpot API easier, as it provides autocompletion and instant access to documentation.

### What are plugin.ts and plugin.js files?

The `plugin.ts` file is where you write code to interact with the Penpot API using TypeScript. This file is then compiled into `plugin.js` which is the final JavaScript code that runs the plugin. You don't write `plugin.js` directly; it's generated from the `plugin.ts` file.

**Note that this is also the only file where you can use the Penpot object.** Do not try to use the Penpot object in your plugin interface scripts.

### What is manifest.json file?

The `manifest.json` file contains the basic information about the plugin. It defines the plugin's name, description, the main code file, and the permissions it requires. The structure of the `manifest.json` file looks like this:

```json
{
  "name": "Your plugin name",
  "description": "Your plugin description",
  "code": "plugin.js",
  "icon": "Your icon",
  "permissions": [
    "content:read",
    "content:write",
    "library:read",
    "library:write",
    "user:read"
  ]
}
```

This file is essential for the plugin to function correctly within Penpot.

## Getting started

### Use this template

To start using the GitHub template repository, follow one of these steps:

#### Method 1: Template Button

Click the "Use this template" button at the top of the repository page on GitHub. This creates a new repository in your account with all the template files.

Now that your repository was created you can clone it in your machine to start working with it:

```bash
git clone <your-repository-url>
cd <your-project-name>
```

#### Method 2: Download the Repository:

Alternatively, you can download the template directly as a ZIP file. Click the "Code" button, then select "Download ZIP." Extract the files to your local machine and start working with them.

### Installation

This project comes with a few dependencies by default, which are necessary for it to function properly. To install these dependencies, navigate to the project directory and run the following command:

```bash
npm install
```

The default dependencies include:

- **`@penpot/plugin-styles`**: contains styles to help build the UI for Penpot plugins. To check the styles go to [Plugin styles](https://penpot-plugins-styles.pages.dev/).
- **`@penpot/plugin-types`**: contains the typings for the [Penpot Plugin API](https://penpot-plugins-api-doc.pages.dev/).
- **`typescript`**: for writing and compiling TypeScript code.
- **`live-server`**: for running a local development server with live reloading.

Running the npm install command will automatically download and install all of these dependencies.

### Usage

To work with your plugin, you can use the following commands:

- **`npm run dev`**: This command performs two actions:

  - It compiles the `plugin.ts` file into `plugin.js`, ensuring your TypeScript code is converted into JavaScript.
  - It starts the live server, allowing you to view and test your plugin in real-time as you make changes.

- **`npm run serve`**: This command only starts the live server, without compiling the `plugin.ts` file. Use this if you only need to run the server and your `plugin.js` file is already up to date.

These commands help streamline your development process by managing both code compilation and local server operations.

### Loading your local plugin

To load and test your local plugin running on `http://localhost:8080`, follow these steps:

1. **Open the Plugin Manager:** In [Penpot (early)](https://early.penpot.dev), use the shortcut `Ctrl + Alt + P` in any file to open the Plugin Manager modal.

2. **Enter the manifest URL:** In the Plugin Manager, provide the URL for your local plugin's manifest file. For a local setup, this URL will be: `http://localhost:8080/manifest.json`

3. **Install the plugin:** After entering the URL, Penpot will attempt to install the plugin. If there are no issues, the plugin will be successfully installed.

4. **Access the plugin:** Once installed, you can open and use the plugin directly from within Penpot whenever you need it.

### Deployment

To prepare your plugin for deployment, follow these steps:

1. **Compile the code:** Use the following command to compile the `plugin.ts` file into `plugin.js`:

   ```bash
   npm run compile
   ```

   This ensures that your TypeScript code is converted into JavaScript, ready for use.

2. **Deploy the source folder:** After compiling, deploy the `src` folder, which contains all your code, including both `plugin.ts` and the compiled `plugin.js`. This is the folder you’ll deploy to your production environment or distribution platform.

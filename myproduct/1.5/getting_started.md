# Getting Started with Ext JS and npm
This guide covers creating an Ext JS application using npm. 

## Component Examples
Use `<text/>` when using html web components.
This tabs component is included with the docs build.

Example of the tabs component.
```
<text>
<sencha-tabs-simple tabsize='150px'>
  <tab title='Modern'>
     <sencha-fiddle id='35ee' />
  </tab>
  <tab title='Classic'>
    <sencha-fiddle id='35ef' />
  </tab>
</sencha-tabs-simple> 
</text>
```

Demo of the `<text/>` and component `<sencha-component-tabs/>` usage. 
<text>
<sencha-component-tabs tabsize='150px'>
  <tab title='Modern'>
     <sencha-fiddle id='35ee' />
  </tab>
  <tab title='Classic'>
    <sencha-fiddle id='35ef' />
  </tab>
</sencha-component-tabs> 
</text>


## Requirements
These are required to use the steps below. 

* <a href='https://nodejs.org/en/download/' target='_blank'>Node.js® 8.11+</a>
* <a href='https://nodejs.org/en/download/' target='_blank'>npm 6+</a>
* <a href='https://java.com/' target='_blank'>Java 8 or 11+</a>


## Retrieve your npm Repository Access Credentials
You'll need access to the npm Repository. There are two ways to get acces, sign up for a trial or purchase a subscription.

### Start a Trial
* [Sign up for a trial](https://www.sencha.com/products/evaluate/) to get access to our npm repo.


### Purchase a Subscription
Existing customers will have access to the npm repo. [Find out more about the subscription options here.](https://www.sencha.com/store/)


## Generate the Ext JS Application

### Step 1: Login to the npm Repository
Use your trial or existing npm credentials to log into the npm repository with the `@sencha` scope.

```
npm login --registry=https://npm.sencha.com --scope=@sencha
```

**Note:**  Your email is used for a username where the `@` character switched to `'..'` two periods, for example `name@gmail.com` converts to `name..gmail.com`. 

### Step 2: Install the App Generator CLI
Install the Ext JS app generator CLI command tool `ext-gen` which will be used to generate the application.

```
npm install -g @sencha/ext-gen
```

### Step 3: Generate the Application
Generate the Ext JS application using the interactive walkthrough. Use `ext-gen app -a` to skip the interactive walkthrough. 

```
ext-gen app -i
```

**CLI Walkthrough**

  *Would you like to see the defaults for package.json?* `(y/N)` 

      If you select `yes`, ext-gen shows all defaults for package.json
      
  *Would you like to create a package.json file with defaults?* `(Y/n)`
   
      This creates a package.json with the defaults

  *What would you like to name your Ext JS app?* (MyApp) 

      Type name of your app

  *What type of Ext JS template do you want?* (Use arrow keys)

      ❯ make a selection from a list
        type a folder name

  *What Ext JS template would you like to use?* 

        classicdesktop
        classicdesktoplogin
        moderndesktop
        moderndesktopminimal
        universalclassicmodern
      ❯ universalmodern

  *Would you like to generate the Ext JS npm project with above config now?* `(Y/n)`
  
      Last question, will output the results. 


### Step 4: Run the New Application
Start up the newly created application in the default browser with these commands. 

* `cd ./<your-app-name>`
* `npm start`


### Step 5: Modify the Application
The resulting app uses the webpack-dev-server. 
So any changes you make will be immediately reflected in the browser.

* Modify your source code. 
* Then check the browser, it will auto reload and update with the new changes.


## What's Next

* [Building Layouts](/extjs/7.0.0/guides/core_concepts/layouts.html)


## Reference

### App Generation CLI Options
Here's a list of the CLI options you could use to generate your application. 

Example:
```
ext-gen app (-h) (-d) (-i) (-t 'template') (-m 'moderntheme') (-c 'classictheme') (-n 'name') (-f 'folder')
```

| CLI Options        |  Alias        | Description | 
|--------------------|---------------|-------------|
| -h                 | --help        | show help (no parameters also shows help) |
| -d                 | --defaults    |  show defaults for package.json |
| -i                 | --interactive |  run in interactive mode (question prompts will display) |
| -t                 | --template    | name for Ext JS template used for generate |
| -c                 | --classictheme|  theme name for Ext JS classic toolkit (not in Community Edition)|
| -m                 | --moderntheme | theme name for Ext JS modern toolkit|
| -n                 | --name        |  name for Ext JS generated app |
| -f                 | --folder      |  folder name for Ext JS application (not implemented yet) |
| -v                 | --verbose     |  verbose npm messages (for problems only) |

### Available App Templates
There are several app templates to generate your application from. Set the `--template` property with one of the options below.

Example:
```
ext-gen app --template universalmodern --moderntheme theme-material --name CoolUniversalApp
```

| Templates              | Target Platforms | Description     | 
|------------------------| ---------------- | ----------------| 
| classicdesktop         | Desktop | Classic toolkit desktop App template. |
| classicdesktoplogin    | Desktop | Classic toolkit desktop App with login template. |
| moderndesktop          | Dekstop | Modern toolkit desktop App template. |
| moderndesktopminimal   | Desktop | Modern toolkit with simple desktop App template. |
| &nbsp;                 | | |
| universalclassicmodern | Mobile & Desktop | Mobile Modern toolkit & Classic toolkit desktop App template. | 
| universalmodern        | Mobile & Desktop | This is a modern and universal template. |


### Available Themes
These themes are available in the ext-gen app generation. Set the `--classictheme` or `--moderntheme` properties with one of the options below. 

Example:
```
ext-gen app --template universalmodern --moderntheme theme-material --name CoolUniversalApp
```

| Theme Options | Available in Toolkit|
|---|---|
| **Modern Toolkit Themes** | |
| theme-material | Modern Toolkit |
| theme-ios | Modern Toolkit| 
| theme-neptune | Modern Toolkit |
| theme-triton | Modern Toolkit | 
| &nbsp; | |
| **Classic Toolkit Themes** | |
| theme-classic | Classic Toolkit |
| theme-material | Classic Toolkit |
| theme-neptune | Classic Toolkit |
| theme-neptune-touch | Classic Toolkit |
| theme-crisp | Classic Toolkit |
| theme-crisp-touch | Classic Toolkit |
| theme-triton | Classic Toolkit |
| theme-graphite | Classic Toolkit |
| theme-material | Classic Toolkit |



Westpac Starter-Pack
====================

> A grunt workflow to get you started with your GUI multi-brand project.

This is a starter pack to help you work in a multi-brand, best-practice kinda way.  
It will:

- [x] [Create the folder structure](#create-folders)
- [x] [Install some preselected templates](#start-with-templates)
- [x] [Run your project and watch for changes](#running)
- [x] [And Version your project](#cache-busting-and-new-versions) (yay!)


#### To read more about the theme and how to use it, visit: [GEL](http://info.westpac.com.au/cx/GEL/)
#### For even more on about how we work, read the [Wiki](https://github.com/WestpacCXTeam/Starter-Pack/wiki)

If you have any suggestions, questions or bugs please [raise an issue](https://github.com/WestpacCXTeam/Starter-Pack/issues).


----------------------------------------------------------------------------------------------------------------------------------------------------------------


# Content

* [Installing](#installing)
* [Setting up](#setting-up)
* [Templating](#templating)
* [Running](#running)
* [Editing](#editing)
* [Cache busting](#cache-busting)
* [Delivering](#delivering)
* [Branches](#branches)
* [Folder structure](#folder-structure)
* [Release History](#release-history)


----------------------------------------------------------------------------------------------------------------------------------------------------------------


# Installing

### MAC
1. Download [NodeJS](http://nodejs.org/) and install on your computer _(We recommend to use [homebrew](http://brew.sh) for the install)_.
1. Run `npm install npm -g` to update to the newest NPM version.
1. Run `npm install -g grunt-cli` to install grunt globally (You might need to install the xCode command line tools)

### PC
1. Download [NodeJS](http://nodejs.org/) and install on your computer.
1. Run `npm install npm -g` to update to the newest NPM version.
1. Run `npm install -g grunt-cli` to install grunt globally

### Both
1. [Download this repo](https://github.com/WestpacCXTeam/Starter-Pack/archive/master.zip) and unpack it into a folder of your choice.
1. `cd` into the folder e.g. `cd c:/Users/MYNAME/Sites/MYPROJECT` within your shell enviroment.
1. Run `npm install` to install all dependencies. Go get a cup of tea, this may take some time.

**[⬆ back to top](#content)**


----------------------------------------------------------------------------------------------------------------------------------------------------------------


# Setting up

The first time after you installed all packages run the command below to setup your folders, the name of your project, the GUI files and all the other goodies
that come with the Starter-Pack.

```shell
grunt setup
```

The setup will save your projects name and version in the `package.json`.

```JSON
{
	"name": "YOUR-NAME-HERE",
	"version": "YOUR-VERSION-HERE",
	"private": true,
	"devDependencies": {
	etc...
```

And depending on what kind of template you chose we'll throw in some js, less and HTML files to get you running asap.

> Remember to include a jQuery version if you chose to use the theme download option.

**[⬆ back to top](#content)**


----------------------------------------------------------------------------------------------------------------------------------------------------------------


# Templating

The Starter Pack comes currently with four templates:

* **`Angular SPA`** with library files and prepared folders plus less files with settings for each brand and some commonly used HTMLincludes.
* **`Javascript application`** setup with no dependencies and prepared folders plus less files with settings for each brand and some commonly used HTMLincludes.
* **`Only less`** files with settings for each brand plus some commonly used HTMLincludes.
* **`A clean start`** without any assumtions about your project plus some commonly used HTMLincludes.


**`A clean start`**

> This is the base of all templates. It includes some commonly used HTMLincludes and a very basic less setup.


```shell
.
├── _BOM
│   └── _less
│       ├── _settings.less
│       └── colors.less
│
├── _BSA
│   └── _less
│       ├── _settings.less
│       └── colors.less
│
├── _CORE
│   ├── _HTML
│   │   └── index.html
│   │
│   ├── _HTMLincludes
│   │   ├── defaults
│   │   │   ├── svgs.html
│   │   │   ├── theme-foot.html
│   │   │   └── theme-head.html
│   │   │
│   │   ├── modernizr.html
│   │   └── windows.html
│   │
│   └── _less
│       └── site.less
│
├── _STG
│   └── _less
│       ├── _settings.less
│       └── colors.less
│
└── _WBC
    └── _less
        ├── _settings.less
        └── colors.less
```


**`Only less`**

> This template includes the `A clean start`-template but adds more less files and suggests a good modular setup for your less workflow.


```shell
.
├── _BOM
│   └── _less
│       ├── _settings.less
│       └── colors.less
│
├── _BSA
│   └── _less
│       ├── _settings.less
│       └── colors.less
│
├── _CORE
│   ├── _HTML
│   │   └── index.html
│   │
│   └── _less
│       ├── base
│       │   ├── fonts.less
│       │   ├── mixins.less
│       │   ├── print.less
│       │   ├── scaffolding.less
│       │   └── type.less
│       │
│       ├── modules
│       │   └── module.less
│       │
│       └── site.less
│
├── _STG
│   └── _less
│       ├── _settings.less
│       └── colors.less
│
└── _WBC
    └── _less
        ├── _settings.less
        └── colors.less
```


**`Javascript application`**

> This template includes the `A clean start`-template and the `Only less`-template and extends it with a basic javascript modular setup with debugging methods
> and two example modules to illustrate the workflow.


```shell
.
└── _CORE
    ├── _HTML
    │   └── index.html
    │
    └── _js
        ├── 010.app.js
        ├── 010.libs
        ├── 020.module1.js
        ├── 030.module2.js
        └── 040.init.js
```


**`Angular SPA`**

> This template also includes the `A clean start`-template and the `Only less`-template but adds an angular SPA startpoint with some libraries and unit tests.

```shell
.
└── _CORE
    ├── _HTML
    │   ├── index.html
    │   │
    │   └── views
    │       └── state1.html
    │
    ├── _js
    │   ├── 010.libs
    │   │   ├── 010.angular.min.js
    │   │   ├── 020.angular-ui-router.min.js
    │   │   ├── 030.jquery-1.9.1.min.js
    │   │   ├── 040.ui-bootstrap-tpls-0.11.2.min.js
    │   │   ├── 050.es5-shim.min.js
    │   │   ├── 060.html5shiv.js
    │   │   ├── 070.json3.min.js
    │   │   ├── 080.respond.min.js
    │   │   ├── 090.underscore-min.js
    │   │   └── 100.angular-cookies.min.js
    │   │
    │   ├── 020.directives
    │   │   └── 010.common.directives.js
    │   │
    │   ├── 050.factories
    │   │   └── 010.common.factories.js
    │   │
    │   ├── 060.controllers
    │   │   └── 010.common.controllers.js
    │   │
    │   ├── 070.common
    │   │   └── 010.main.js
    │   │
    │   └── _tests
    │       ├── 010.lib
    │       │   └── 010.angular-mocks.js
    │       │
    │       ├── 020.services
    │       │   ├── 010.servicePromiseTest.js
    │       │   ├── 020.serviceTest.js
    │       │   ├── 030.stateTest.js
    │       │   └── 040.twitterAPIServiceTest.js
    │       │
    │       └── 030.mocks
    │           └── 010.stateMock.js
    │
    └── _mock
        └── mock.json
```

**[⬆ back to top](#content)**


----------------------------------------------------------------------------------------------------------------------------------------------------------------


# Running

Now run the default grunt task to watch your files for changes:

```
grunt
```

Visit [http://localhost:9000/](http://localhost:9000/) to see your `PROD` folder.  

> This first time you run `grunt` the script will build your `PROD` folder ready for production (JavaScript is uglified) and start the watch.
> Once you change a file the watch **will not** uglify your JS code as this would take too long. Instead it just concatenate all JS files together to save time.
> Remember to run `grunt` before you deliver your production code to avoid giving out large JS files.

**[⬆ back to top](#content)**


----------------------------------------------------------------------------------------------------------------------------------------------------------------


# Editing

Now that you have your project setup and running you can go ahead and edit the files you want.

#### _HTML_

Make sure you don't edit any files in the `PROD` folder as this folder is being deleted and regenerated on each change the watch detects.


#### _GUI includes_

All templates come with a set of commonly used HTMLincludes. All you have to do is include them in your files:  

Inside `<head>` of your file:
```HTML
@@include('defaults/theme-head.html')
```

Before the closed `</body>` tag:
```HTML
@@include('defaults/theme-foot.html')
```


#### _Less_

We have supplied you with a couple less files (included in the less and angluar templates).
Use the `settings.less` files in each respective brand folder to add brand specific values like colors.
That way you only have to change the setting files to apply the different brand styles.

The compiled file can be referenced in your HTML with:

```HTML
<link rel="stylesheet" media="all" type="text/css" href="css/--currentVersion--.min.css">
```

_More about the process of file naming in the [next section](#cache-busting)_


#### _Javascript_

All javascript files found in either `_CORE/_js/` or the brand folders `_BOM/_js/`, `_BSA/_js/`, `_STG/_js/`, `_WBC/_js/` will be concatenated and minified
into one file and referenced in your HTML with:

```HTML
<script type="text/javascript" src="js/--currentVersion--.min.js"></script>
```

_More about the process of file naming in the [next section](#cache-busting)_

> If you are using the theme javascript files make sure to include a jQuery version as the theme depends on a recent version of jQuery!


#### _Images_

All images in the `_CORE` and brand folders are minified and moved into the `img/` folder for each brand within the `PROD` folder.


#### _SVG_

SVGs in the `_CORE` and brand folders are running through a [grunticon](https://github.com/filamentgroup/grunticon) task.
This takes the svgs and generates three css files and a `sitepng/` folder with png fallbacks.
This is then put into the `css/` folder with the `--currentVersion--` namespace.
The css classes are prefixed with `sitesymbol-` to avoid overwrites with the GUI.  
To include the compiled file into your HTML use below code in your `<head>`:

```HTML
@@include('defaults/svgs.html')
```


#### _Fonts_

All files in the brand folders `_BOM/_fonts/`, `_BSA/_fonts/`, `_STG/_fonts/`, `_WBC/_fonts/` are moved to `/fonts` in it's respective brand folder within `PROD`.


#### _CSS_

All files in the brand folders `_BOM/_css/`, `_BSA/_css/`, `_STG/_css/`, `_WBC/_css/` are moved to `/css` in it's respective brand folder within `PROD`.


#### _Watch_

The build in watch is looking at all relevant files and evokes the appropriate tasks when one of these changes.

> This first time you run `grunt` the script will build your `PROD` folder ready for production (JavaScript is uglified) and start the watch.
> Once you change a file the watch **will not** uglify your JS code as this would take too long. Instead it just concatenate all JS files together to save time.
> Remember to run `grunt` before you deliver your production code to avoid giving out large JS files.

**[⬆ back to top](#content)**


----------------------------------------------------------------------------------------------------------------------------------------------------------------


# Cache busting

Run the below code to bump up to the next version and cache bust your application:

```
grunt bump
```

If you want to reference the new version string in your HTML, JS or CSS just use this:

```
--currentVersion--
```

This string will be replaced by grunt with the current version string. Both CSS and Javascript files that are compiled for you will be named according to your
name and the version of your project.

To include your Javascript, CSS files use:
```HTML
<script type="text/javascript" src="js/--currentVersion--.min.js"></script>
```
and
```HTML
<link rel="stylesheet" media="all" type="text/css" href="css/--currentVersion--.min.css">
```

**[⬆ back to top](#content)**


----------------------------------------------------------------------------------------------------------------------------------------------------------------


# Delivering

We have created some tools to help with the HTML deliverable:

* A Chrome bookmarklet to show you the grid overlay, [install gridly](https://github.com/dominikwilkowski/gridly)
* A chrome extension for your dev tools to map colors to it's tints, [install GEL inspector](https://github.com/dominikwilkowski/GEL-inspector)

**[⬆ back to top](#content)**

----------------------------------------------------------------------------------------------------------------------------------------------------------------


# Branches

We are maintaining two branches here:

* [master](https://github.com/WestpacCXTeam/Starter-Pack/tree/master) -> This branch has a stable running version of the Starter Pack.  
  _Please only use this branch for development of new GUI applications._
* [dev](https://github.com/WestpacCXTeam/Starter-Pack/tree/dev) -> In `dev` we work on new features and this branch might be a bit off at times.

**[⬆ back to top](#content)**


----------------------------------------------------------------------------------------------------------------------------------------------------------------


# Folder structure

The below folder structure will explain what goes where:  
_(get ready to scroll...)_

```
.
├── _BOM                                 // BRAND FOLDER FOR BOM (1)
├── _BSA                                 // BRAND FOLDER FOR BSA (1)
├── _STG                                 // BRAND FOLDER FOR STG (1)
├── _WBC                                 // BRAND FOLDER FOR WBC (1)
│   │
│   ├── _css                             // The _css brand folder (2)
│   │   ├── png
│   │   └── theme.min.css
│   │
│   ├── _fonts                           // The _fonts brand folder (3)
│   │   ├── font.eot
│   │   ├── font.svg
│   │   └── font.ttf
│   │
│   ├── _HTMLincludes                    // The _HTMLincludes folder (4)
│   │   └── logo.html
│   │
│   ├── _img                             // The _img brand folder (5)
│   │   ├── image.jpg
│   │   └── banner.png
│   │
│   ├── _js                              // The _js brand folder (6)
│   │   ├── libs
│   │   ├── polyfills
│   │   │   ├── modernizr.js
│   │   │   └── polyfills.js
│   │   └── theme.min.js
│   │
│   ├── _less                            // The _less brand folder (7)
│   │   └── _settings.less               // The _settings.less file (8)
│   │
│   └── _svg                             // The _svg brand folder (9)
│       └── symbol.svg
│
│
│
├── PROD                                 // THE PROD FOLDER (10)
│   ├── BOM
│   ├── BSA
│   ├── STG
│   └── WBC
│
│
│
└── _CORE                                // THE _CORE FOLDER (11)
    │
    ├── _HTML                            // The _HTML core folder (12)
    │   ├── templates
    │   │   └── template1.html
    │   ├── views
    │   │   └── state1.html
    │   └── index.html
    │
    ├── _HTMLincludes                    // The _HTMLincludes core folder (13)
    │   ├── defaults
    │   │   ├── svgs.html
    │   │   ├── theme-foot.html
    │   │   └── theme-head.html
    │   ├── modernizr.html
    │   └── windows.html
    │
    ├── _js                              // The _js core folder (14)
    │   ├── 010.libs
    │   ├── 020.directives
    │   ├── 030.services
    │   ├── 040.filters
    │   ├── 050.factories
    │   ├── 060.controllers
    │   ├── 070.common
    │   └── _tests                       // The tests core folder (15)
    │
    ├── _mock                            // The _mock core folder (16)
    │
    └── _less                            // The _less core folder (17)
        ├── base
        │   ├── fonts.less
        │   ├── mixins.less
        │   ├── print.less
        │   ├── scaffolding.less
        │   └── type.less
        │
        ├── modules
        │   └── module.less
        │
        └── site.less                    // The site.less file (18)
```


### BRAND FOLDER FOR _BOM/_BSA/_STG/_WBC (1)

The brand folders represent the difference of the codebase between each other.
So files in the brand folders are uniqe to that brand.
Files changed here will feed into its counterpart in `PROD`.


### The _css brand folder (2)

Files in here will automatically copy to its counterpart folder in `PROD`.
This is the place to add the GUI and some of its files e.g.: `theme.min.css` or `png/`.


### The _fonts brand folder (3)

Files in here will automatically copy to its counterpart folder in `PROD`.
There are some GUI font files that will fit in here.


### The _HTMLincludes folder (4)

You can merge two HTML files into on with a simple code snippet like:

```
@@include('defaults/modernizr.html')
```

We use `[grunt-include-replace](https://github.com/alanshaw/grunt-include-replace)` for this and you can learn about it in their readme.

_Note: you can also organize your `_HTMLincludes` folder in subfolders_


### The _img brand folder (5)

Images in here will be minified and copied to its counterpart folder in `PROD`.


### The _js brand folder (6)

Files in here will automatically copy to its counterpart folder in `PROD`.
There are some GUI js files that will fit in here including `theme.min.js` and `polyfills.js`, these are essential in having an application that works cross browser.

> Remember to include your own copy of jQuery if you are using the theme.min.js

We have taken the time to include some default libraries to get you started in the angular template.
It's worth noting that we are not using Angulars' default routing in this version of our SPA. We have chosen to use
[ui-router](https://github.com/angular-ui/ui-router).

The unit testing framework we suggest is [Jasmine](http://jasmine.github.io/)


### The _less brand folder (7)

Organise your less file here for each brand.
Try to use only the settings file where you overwrite the colors and you don't need to repeat yourself.
Include this file by pasting the following snippet into your header:

```
<link rel="stylesheet" media="all" type="text/css" href="css/--currentVersion--.min.css">
```


### The _settings.less file (8)

The `_settings.less` file is referenced by the grunt task and includes the `_CORE` less files.
This is where you have the settings for each brand which are then referenced in your `_CORE` files.


### The _svg brand folder (9)

SVG files in here will be minified and run through a grunticon task. The resulting files are:
- `--currentVersion--.data.png.css`
- `--currentVersion--.data.svg.css`
- `--currentVersion--.data.fallback.css`
- `sitepng/`

Include these into your site by pasting the follwoing snippet into your header:

```HTML
<script>window.grunticon=function(e){if(e&&3===e.length){var t=window,n=!(!t.document.createElementNS||!t.document.createElementNS("http://www.w3.org/2000/svg","svg").createSVGRect||!document.implementation.hasFeature("http://www.w3.org/TR/SVG11/feature#Image","1.1")||window.opera&&-1===navigator.userAgent.indexOf("Chrome")),o=function(o){var r=t.document.createElement("link"),a=t.document.getElementsByTagName("script")[0];r.rel="stylesheet",r.href=e[o&&n?0:o?1:2],a.parentNode.insertBefore(r,a)},r=new t.Image;r.onerror=function(){o(!1)},r.onload=function(){o(1===r.width&&1===r.height)},r.src="data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///ywAAAAAAQABAAACAUwAOw=="}};grunticon( [ "css/--currentVersion--.data.svg.css", "css/--currentVersion--.data.png.css", "css/--currentVersion--.fallback.css" ] );</script>
<noscript><link href="css/--currentVersion--.fallback.css" rel="stylesheet"></noscript>
```

_Note: we included an `HTMLinclude` snippet for you that you only need to uncomment in the index file_


----------------------------------------------------------------------------------------------------------------------------------------------------------------


### THE PROD FOLDER (10)

The `PROD` folder is where all files are compiled to.
Each brand has its own folder and should be runnable with the build in server on [http://localhost:9000/](http://localhost:9000/).
*Do not change anything in here as this folder will be deleted and recreated on each iteration*


----------------------------------------------------------------------------------------------------------------------------------------------------------------


### THE _CORE FOLDER (11)

The `_CORE` folder is where all files sit that are the same on each brand. Try to keep as much in here as possible to keep all brands consistent.


### The _HTML core folder (12)

This folder should contain all of your HTML files. Organise them into subfolders to keep them clean.

_Remember: you can use your [_HTMLincludes](#the-_htmlincludes-folder-4) to brand these files._


### The _HTMLincludes core folder (13)

The _HTMLincludes folder is copied into each branch folder, then the brand folders override all the files for each brand.
We use `[grunt-include-replace](https://github.com/alanshaw/grunt-include-replace)` for this and you can learn about it in their readme.


### The _js core folder (14)

There are some GUI js files that will fit in here including `theme.min.js` and `polyfills.js`, these are essential in having an application that works cross browser.

We have taken the time to include some default libraries to get you started in the [angular branch](https://github.com/WestpacCXTeam/Starter-Pack/tree/angular).
It's worth noting that we are not using Angulars' default routing in this version
of our SPA. We have chosen to use [ui-router](https://github.com/angular-ui/ui-router)


### The tests core folder (15)

The tests folder is a place not only to put the tests themselves, but also reference the libraries as well.
If you want to use any of the angular goodness in your project then copy the dependencies into the tests/libs folder.


### The _mock core folder (16)

The mock folder is predominantly for mock API calls. Use it to store JSON structures.


### The _less core folder (17)

Organise your less project here. We have provided a starting point for you in this repo.


### The site.less file (18)

The `site.less` file should be referenced by the brand `_settings.less` and only includes all modules from the filesystem.

_Remember: Less files are cheap and so is documentation in less_

**[⬆ back to top](#content)**


----------------------------------------------------------------------------------------------------------------------------------------------------------------


# Release History
* 1.1.3 - Fixed some syntax bugs
* 1.1.2 - Moved HTMLincludes to `[grunt-include-replace](https://github.com/alanshaw/grunt-include-replace)`
* 1.1.1 - Added `javascript` template and documentation
* 1.1.0 - Added Yeoman like character, better watch, more documentation
* 1.0.0 - Fixed bugs, added better watch, questionnaire

**[⬆ back to top](#content)**


# };
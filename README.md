markupBuilder
=============

Markup builder on gulp
Use Jade as templater, scss as preprocessor for css.

You have to install `nodeJS` and `npm` for using markupBuilder.
Also you need Java for webfont generator. If you are not going to generate fonts, you don't need it.

Installation
------------

    npm i or npm install

Install gulp, webfonts globaly and all dependencies.  

    gulp init

Create fonts, images (with subdirs), js/libs and js/plugins directories. Create assets folder inside template module.      

If you use Windows, you have to add key `--ms`.

Descritpion
-----------

Markup is the main folder of project. There are modules, scss-files and templates of pages. Also you can find images, fonts and js folders.
Even module is a part of page, for example — «header». 
Even module has it's own temaplte, scss-files, js and images.
There are templates of pages in root directory of markup. To create new page just create new file with the name of the page.

Modules have to be included into the pages templates. Also modules could include other modules.

You shouldn't use prefixes in css, autoprefixer do it itself. JSHint will check yor js-code.


Main commands
-------------

`gulp clean` — clean dev directory.

`gulp dev` — development task. Create compiled project and watch for changes in project's files. Call clean task.

`gulp build-dev` — just generate dev version of project.

`gulp build` — create build version of project.

If you need to generate woff, eot and svg files of your font, you can use key `--gf`. 
Example: `gulp build --gf`. This command build project and generate fonts files into fonts folder in build. All you need is ttf-file of your font in folder fonts in root directory.

File structure
--------------

* Project file structure

    - markup — main folder, has modules, scss and templates of pages.
        - fonts — folder for fonts.
        - images — folder for images.
            - content — images in content (images in articles and etc.)
            - plugins — images for plugins. There are could be files and directories
            - sprite — images for sprite. Even image has to be named with unique name, which will be use in css to paste sprited image.
        - js — folder for js.
            - html5shiv — folder with htm5shiv. 
            - libs - folder for js-libs like jquery
            - plugins — folder for plugins js
        - modules — folder with modules.
            - _template — folder with module.
                - assets — for the module.
                - _template.jade — template of the module.
                - _template.js — js file of the module.
                - _template.scss — scss file of the module.
        - scss — folder with scss.
            - common.scss — common stylies for project (not required)
            - GUI.scss — GUI-elements stylies (not required)
            - mixins.scss — mixins (not required)
            - reset.scss — reset css (not required)
            - sprite.scss — scss for sprite generator
            - vars.scss — vars of the project (not required)
        - developer.scss — scss file for developers stylies. Required! 
        - main.scss — main file for scss. All scss files include into this file.
        - _template.jade — template of the page.

* Dev version of compiled project
    
    - css — folder with css.
    - fonts — folder with fonts.
    - img — folder with images.
        - assets — folder with images for modules.
        - content — folder with images for content.
        - plugins — folder with images for plugins.
        - sprite.png — sprite image.
    - js — folder with js.
        - html5shiv — folder with js-files which have to be separate. There are htm5shiv. 
        - libs - folder for js-libs like jquery.
        - main.js — main.js file.

    - template.html — generated template


* Build version is a copy of dev version, but it has minified version of css and js files. There are no any console.log and debugger code in js.
Each build dir has it's own version. Version is a date of building.


TODO
----

* Image optimazer.
* Livereload (may be)
* Creating zip-archive of build version
* Notify including
* Each task in their own folders
* Jshint for scss
* Less (may be)

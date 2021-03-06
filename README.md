# Bytecode Digital Agency B.V. Coding Standards

[![Developed by](https://img.shields.io/badge/Developed%20by-Bytecode.nl-green.svg)](https://bytecode.nl) [![GPL Licence](https://badges.frapsoft.com/os/gpl/gpl.svg?v=103)](https://opensource.org/licenses/GPL-3.0/) [![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badges/)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FBytecodeBV%2FCoding-Standards.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2FBytecodeBV%2FCoding-Standards?ref=badge_shield)

[![Build Status](https://travis-ci.org/BytecodeBV/Coding-Standards.svg?branch=master)](https://travis-ci.org/BytecodeBV/Coding-Standards)
[![dependencies Status](https://david-dm.org/BytecodeBV/Coding-Standards/status.svg)](https://david-dm.org/BytecodeBV/Coding-Standards)
[![devDependencies Status](https://david-dm.org/BytecodeBV/Coding-Standards/dev-status.svg)](https://david-dm.org/BytecodeBV/Coding-Standards?type=dev)
[![Known Vulnerabilities](https://snyk.io/test/github/bytecodebv/coding-standards/badge.svg?targetFile=package.json)](https://snyk.io/test/github/bytecodebv/coding-standards?targetFile=package.json)
[![bitHound Overall Score](https://www.bithound.io/github/BytecodeBV/Coding-Standards/badges/score.svg)](https://www.bithound.io/github/BytecodeBV/Coding-Standards)

[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)
[![CodeFactor](https://www.codefactor.io/repository/github/bytecodebv/coding-standards/badge)](https://www.codefactor.io/repository/github/bytecodebv/coding-standards)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/7ec94c3910f7440a9552b686741b3499)](https://www.codacy.com/app/lucianonooijen/Coding-Standards?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=BytecodeBV/Coding-Standards&amp;utm_campaign=Badge_Grade)
[![BCH compliance](https://bettercodehub.com/edge/badge/BytecodeBV/Coding-Standards?branch=master)](https://bettercodehub.com/)
[![bitHound Code](https://www.bithound.io/github/BytecodeBV/Coding-Standards/badges/code.svg)](https://www.bithound.io/github/BytecodeBV/Coding-Standards)
[![Maintainability](https://api.codeclimate.com/v1/badges/341030401d2b34a42344/maintainability)](https://codeclimate.com/github/BytecodeBV/Coding-Standards/maintainability)

## About

The coding standards for developers at Bytecode Digital Agency B.V. to ensure code health and quality of the products delivered to our clients.

Please use these standards in every line of code you write. This is not to bully you but to make sure everyone in our company writes code the same way, and this is the only way to assure quality of our code.

This repo also contains files you can use for development. These files are *defaults*, so you can of course edit them to suit the needs of the project.

Please read this file thoroughly, and also check out the links in the [Final words](#final-words) section. Spending half an hour now can save you many hours during projects!

Remark: _This project also includes our Parcel starter_

# Table of Contents

We will discuss the following points in this Coding Standards file:

* [General](#general)
* [General Style](#general_style)
* [Security](#security)
* [Git](#git)
* [HTML](#html)
* [CSS](#css)
* [CSS-preprocessors](#css-preprocessors)
* [Javascript](#javascript)
* [PHP](#php)
* [WordPress](#wordpress)

# General

These are the general rules we use for writing software.

* **Write clean code!**
* Structure your work in a way that other developers can easily understand it. This means having the possibility of co-workers modifying your code in the back of your mind
* Document your code for end users, and when writing small and general functions
* [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself): Don't repeat yourself! Don't build long functions that do a specific thing, but try to create smaller and more general functions
* When writing a part of a project that is essential to other systems, write unit tests to make sure these systems can depend on your code
* When starting on a project, try to pick the best tool for the job. Be sure to discuss this with your superior, as this can have a lot of impact on a project
* Use a clean folder structure. There is no default folder structure, because this depends on the kind of product. Just to be sure your colleagues can work with your code, discuss your proposal for the project folder structure with your superior
* Write your code with the latest techniques, and let tools like Babel or PostCSS take care of backwards compatibility
* For production, uglify/minify your code and remove source maps
* All communication on Jira and all documentation (and everything else in Git repos) should be in English

# General Style

* Don't use "Yoda" conditions, as these make it harder to read your code at a glance
* Use camelCase and use single quotes (unless the language does not allow this). This is mostly taken care of by our linters
* Indent using 4 _spaces_. Set your code editor to convert tabs to 4 spaces.
* Lines should be at most 80 characters (spaces included). This is also taken care of by our linters
* For single line comments, use `// comment`, for multi-line comments, use `/** * comment */`
* Make sure your code is readable. This means using clear names for your functions, adding enough (although not too many) comments and adding enough and a consistent amount of whitespace. The latter is mostly taken care of by our linters.
* On that subject: use linters, and let the linter check your code before committing on Git. You can also use git-hooks to lint your code as you commit
* Leave an empty last line in every file
* If the project allows it, unit and integration tests are highly appreciated

# Security

* For security reasons try to avoid using FTP, rather use SFTP or connect through SSH and pull from the Git repo (with a deploy key)
* When using SSH, if possible, use an SSH-key and not just a password. This is to improve security
* For deployment using Git, or when setting up Git on a remote server, always use deploy keys, and do not reuse these keys
* When you add any login credentials or keys in a Git repo, even if it's a private repo with limited access, encrypt the files containing the credentials/keys if possible for maximum security

# Git

* Don't merge your own code into the develop/master branch, always create a pull request and let at least one other developer review the code
* Work on your own branch and name the branch to your first name. If Jira is used for the project, you can name the branch after the issue name in Jira
* Make sure you always add steps in the README.md file for others to make your code run: include the needed global dependencies, commands to install dependencies, and steps to run everything.
* Git README.md badges are sexy. Add them! For examples, check the top of this repo
* To make sure your project will run on the computer of others, use tools like TravisCI, CircleCI or Jenkins
* If your project uses a set of dependencies (like Mongo and Node) working together in a complex way, write a Dockerfile or Docker Compose file
* Write a clear description for your commit which makes clear what was changed or added, fo example: not `"styling updates"`, but rather `"improved styling for the menu dropdown"`
* Before pushing, see if you are pushing the right files and you are not uploading confidential files or files that should not be in the Git repository
* If your commit is to fix a Jira issue, include the issue number in your commit message
* Try to commit at least around every hour or two or after important milestones
* Use [semantic versioning](https://semver.org/) for production releases

# HTML

* Use external files to include styling and scripts (never use in-line styling).
* Use `<link rel="stylesheet" href="style.css">` and not `@import` to add styling. For scripts use `<script src="codeguide.js" />`
* For your own code, you can include just 1 script file and 1 stylesheet, so combine everything using tools like Gulp, Parcel or Webpack
* Add an `alt` tag to images
* Use double quotes like `<a href="#">`, not single quotes like `<a href='#'>`
* Write your code with XHTML in mind, so use `<br/>` and not just `<br>`, because there is always a chance your code will later be converted into a React app. *Side Note: using `<br>` in your HTML is not very semantic, use CSS for white space please* :angel:
* Make us of the HTML5 elements `<article>, <nav>, <aside>, <details>, <header>, <footer>, <section>`, instead of `<div>` where appropriate.
* _Only_ leave an empty line between parts of the page, like the navigation, or `<section>` tags
* For templating, you can always use Handlebars. If you like to use another templating engine like, like Pug or ejs, discuss this with your superior
* Use the following order of attributes on HTML-elements:
  1. src, for, type, href, value
  2. id, name
  3. class
  4. data-*
  5. title, alt
  6. role, aria-*
* Use the following "basic" structure for HTML documents

```html
<!DOCTYPE html>
<html lang="nl">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <meta name="description" content="tekst">
    <meta name="keywords" content="tekst">
    <title>Document</title>
    [css dependencies]
    [font dependencies]
  </head>
  <body>
  Content goes here
  [javascript dependencies]
  </body>
</html>
```

# CSS

* Try not to use CSS, rather use SASS/SCSS
* We strive to use as few CSS frameworks as possible. So only include a CSS framework/library after discussing
* If you are using Bootstrap _(try not to use the whole framework, just the grid system)_, you can use Bootstrap 4, not Bootstrap 3, only if you have to work with legacy code that already includes Bootstrap 3
* If you are using another framework that uses px-units, use px, else use rem-values *(rem values scale with the HTML-object's font-size, which makes responsive typography a whole lot easier)*
* If the used frameworks allow it, write your media queries mobile first, like `@media (min-width: 30rem)`
* List related items together
* If a :hover pseudo class is styled, style :focus the same for accessibility
* Never use IDs, use classes
* Use [BEM](http://getbem.com/naming/) for naming CSS classes
* Name classes descriptively
* Use double quotes, not single quotes
* Use only one declaration per line, this makes the code more readable
* Add a space after the colon of a declaration, so not `margin:1rem;` but `margin: 1rem;`
* For font-sizes, use an exponential scale, preferably based on the Fibonacci number (1.618) [Click here to geek out](https://3.7designs.co/blog/2010/10/how-to-design-using-the-fibonacci-sequence/). There is also a Sass plugin available for modular scales like this. You can find the plugin [here](https://github.com/modularscale/modularscale-sass)
* For colors, use hex values (not rgb or rgba), as short as possible, and in lowercase, for example: not `#FFFFFF` but `#fff`, and not `background-color: #fff` but `background: #fff`
* A zero (0) should not have unit
* Try to work with floats as little as possible, rather use flexbox or CSS grids
* If you are writing emails, use of the MJML preprocessor is encouraged

# CSS preprocessors

* Currently, SCSS is preferred for a project. If you want to use something else, discuss this with your superior.
* Do not use extends, but use mixins
* Make use of the functionalities the preprocessor gives you! Don't do stuff yourself that a preprocessor can take care off for you
* You can compile your code to CSS using toolkits like Webpack or Gulp, although currently Parcel Bundler is the prefered method
* Don't go and add prefixes by hand. Instead, let a plugin handle this for you
* Try to avoid nesting, rather use BEM. Use of nesting is mostly resticted to :hover-states etc.
* When you do nest, make it at most 3 levels deep
* Provide the media queries rules inside the element
* Break files out into small modules (avoid having a file that is larger than 100 lines)
* Avoid using IDs throughout the site. Use IDs for parent elements. Example: Header, Footer, Main. Using Classes avoids having to use !important
* For shameful code, use the *_shame.scss file*. We all have to do this sometimes, better own up to it. [More Geeky links](https://csswizardry.com/2013/04/shame-css/)
* Use the folder structure as given in this project

# Javascript

* If possible, use vanilla Javascript. Don't add jQuery just for a simple DOM manipulation or a simple API call
* Use Yarn as a package manager: [it's better than NPM](https://www.sitepoint.com/yarn-vs-npm/).
* The usage of Typescript is encouraged
* For linting, use ESLint. You're allowed to use modules on top of ESLint like [Prettier](https://prettier.io/)
* Write your code in ESNext/ES6+, and transpile using Babel to ES5 because Internet Explorer :pensive:
* Before adding a library, discuss with your superior
* Don't use anonymous functions (`function test() {}`), write them like this: `const test = () => {}`
* When using jQuery, write it using `$('selector');` and not using `jQuery('selector');`, except when it gives compatiblity issues.
* Comment your code following the [ESDoc](https://esdoc.org/) notation, it's understood by (almost) every code editor and IDE

# PHP

* For server side stuff we prefer using NodeJS over PHP, so only use PHP when necessary
* Use a clean folder structure and use include to add other files. Make sure files don't get longer than 200 lines
* For reasonably sized projects, use the MVC structure
* If you are storing user data, especially passwords, you **must** use a framework like Laravel, because you really *really* shouldn't mess with storing that stuff yourself
* PHP is notorious for ugly code, so be aware of this and write your code *extra* clean
* Always use PHP 7.1+

# WordPress

This is an extension of the PHP part of this file.

* Write your WordPress code along the rules of the [WordPress Codex](https://codex.wordpress.org/)
* Write variables using underscores (snake_case), not camel-case, because WordPress does not allow camel-case, so write variables like `this_is_an_example`
* Don't change anything in the core files or existing plugins/themes! Use hooks, make a plugin out of it, or add it to the child theme
* Don't hardcode paths, use functions like `get_stylesheet_directory_uri`
* Never write MySQL queries yourself, use `$wpdb`
* Enqueue your stylesheets by hand, not just in the style.css file
* For your custom styles and scripts, use Webpack or Gulp
* Use separate development, staging and production environments
* If possible, use the tools from [Roots.io](https://roots.io/)

# Final words

Some final words of this Coding Guidelines file:

#### Sources

The following sources are used for the creation of this Coding Guidelines file, please also read the following sources (you don't have to go in depth), because of course we couldn't add every single usable detail in this file.

* [Airbnb Javascript standards](https://github.com/airbnb/javascript)
* [Javascript project guidelines](https://github.com/wearehive/project-guidelines)
* [Sitepoint SASS project architecture](https://www.sitepoint.com/architecture-sass-project/)
* [SASS Guidelin.es](https://sass-guidelin.es/), please read [this](https://sass-guidelin.es/#too-long-didnt-read) part for some great tips
* [Altavia ACT styleguide](https://github.com/Altavia-ACT/styleguide)
* [Gitignore creator](https://www.gitignore.io/)
* [WordPress Codex](https://codex.wordpress.org/)
* [Roots.io](https://roots.io/)
* [Wikipedia - DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
* [Fibonacci](https://3.7designs.co/blog/2010/10/how-to-design-using-the-fibonacci-sequence/)
* [Yarn](https://www.sitepoint.com/yarn-vs-npm/)
* [BEM](http://getbem.com/naming/)

#### Starter packs

* This repo for Parcel development
* [Mega Boiler Plate](http://megaboilerplate.com/)
* [HTML-Starter-Kit](https://github.com/AllStarterKits/HTML-Starter-Kit)
* [NodeJS-Starter-Kit](https://github.com/AllStarterKits/NodeJS-Starter-Kit)
* [MEAN-Starter-Kit](https://github.com/AllStarterKits/MEAN-Starter-Kit)
* WordPress framework - coming soon

#### Contributors

* [Luciano Nooijen - Bytecode Digital Agency B.V.](https://bytecode.nl)
* [Jeroen van Steijn - Bytecode Digital Agency B.V.](https://bytecode.nl)


## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FBytecodeBV%2FCoding-Standards.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2FBytecodeBV%2FCoding-Standards?ref=badge_large)
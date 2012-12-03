# LESS Import Architectures Proof of Concept

## Background

This project is a proof of concept for creating a CSS framework using LESS and the @import statement to easily skin applications. I work on a number of projects that utilize a common base layout, but then need to be "skinned" for clients based on a brand's color palette. A brief explanation is below, but please see the source for more commenting.

## Markup
The markup is a simple HTML5 document that has bootstrap button components as well as a simple paragraph element. I am using a client-side JS version of the LESS compiler for this proof, but in real projects we prefer to compile or pre-compile server side for speed.

## Styles
The only CSS file loaded in HTML is the skin. This in turn loads the main application's styles and then updates any vars it needs in the process. The main application style sheet loads 3 style sheets:

1. __bootstrap.less__ - The core bootstrap styles which also does a browser reset.

2. __app-vars.less__ - If we were to run the application without skinning, we could update any bootstrap variable definitions here to create a general style for our application. It's also a good place possible to define more LESS application variables here as needed.

3. __app-ui.less__ - Currently a single file, but we would likely break up our application's css into modular files and load them here. These styles could also leverage bootstrap or new application LESS vars defined in app-vars.less.

## Experiment
Try changing the button variable definitions in skin.less or just comment them out. If commented out, they will default to styles defined in app-vars.less, so try changing those too. If those are commented out as well, you get base bootstrap styles.
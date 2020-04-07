# Rhenania Hinsbeck Typo3 Design Template

This design for the [Rhenania Hinsbeck Webpages](https://www.rhenaniahinsbeck.de) was originally based on a bootstrap template from 
[Start Bootstrap - Clean Blog](https://startbootstrap.com/template-overviews/clean-blog/). 

We started with a fork a while ago, but as this is now so far away from the version of clean blog, the decision was made to create a complete own repository without any forking connection. 
This template is used for a typo3 installation for the [Rhenania Hinsbeck Webpages](https://www.rhenaniahinsbeck.de) and can be used to make design updates regarding the templates (look and feel). 

## Usage

This repository is build as follows:

**css** hold all the css files - note that these must be first created. See **build chapter** for how to build.
**img** all the images for the html template
**js** holding all javascript files
**Layouts** all typo3 layout files are in here
**Partials* all typo3 partial layout files are in here
**scss** these are the source SASS files, so use these if you want to change the css and then build the css files. See **build chapter** for how to build.
**Templates** all the typo3 template files are in here. Have a look also for the files which begin with **maintemplate<xx>.html** as these are the main page templates used for typo3 fluid design.
**ts** holds the typoscript files for constants and for template typoscript code. 
**vendor** all vendor code, e.g. bootstrap, jquery asf is in here. Do not change!

### Change the design

- Clone the repository.
- create a branch.
- Change the files you need to change e.g. scss files, or templates, or images, or Layouts or Partials... e.g.
- Then run `npm install` 
- and then run `gulp` which will build the the css and minifies it from scss and all other things which are needed. 
- commit and push the branch
- create a pull request
- if the pull request is accepted and merged, the changes will automatically copied to the live-server!!!

## Knowledge Base

### Change text for content item from tt_content

Add this into Page-TS config of the root page

```
TCEFORM {
    tt_content {
        layout {
            altLabels {
                0 = Karten Design
                1 = Alternatives Design
            }
            removeItems = 2, 3, 4, 5
        }
    }
}
```

### Fluid Styled content überschreiben

https://www.programmier-tipps.de/2017/12/14/fluid-styled-content-templates-ueberschreiben/ 

```
lib.contentElement {
   templateRootPaths {
      100 = fileadmin/template/Resources/Private/Templates/
   }
   partialRootPaths {
      100 = fileadmin/template/Resources/Private/Partials/
   }
   layoutRootPaths {
      100 = fileadmin/template/Resources/Private/Layouts/
   }
}
```

## To create full html/css/java articles
- Install **JCE Editor** (TODO: explain how)
- Configure JCE Editor to suuport everything:
    - Go to Components - JCE Editor - Profiles - Default
    - Go to Editor Parameters - Advanced
    - Go down to Code Blocks and check all that apply
---
## To add custom CSS
- Install mod_customcss
- Go to Modules and add a new **Custom CSS** module.
- Add your custom CSS either directly, or via loading a file. Make sure you publish, and choose **topbar** for position.
---
## To make sure that everything works fine when using bootstrap
- Create a Custom CSS module (call it CSS - Bootstrap)
- Position **topbar**
- Language **All**
- Go to Advanced and check Yes for "Use an external CSS file?".
- CSS URL: https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css
---
## To make sure that the article title does not show
- Go to the Menus - choose the menu and go to the link for the respective article
- Go to Page Display and set **Show Page Heading** to Hide.
---
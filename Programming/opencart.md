## Change main menu bar color
- Open file **/catalog/view/theme/default/stylesheet/stylesheet.css**.
- Search for **#menu**.
- Change color in **background-image: linear-gradient(to bottom, #004d1a, #006622)**.
---
## Change cart button color
- Open file **/catalog/view/theme/default/stylesheet/stylesheet.css**.
- Search for **.btn-inverse**.
- Change color in **background-image: linear-gradient(to bottom, #ff4444, #ff2222)**.
- Search for **.btn-inverse:hover**.
- Change color in **background-image: linear-gradient(to bottom, #ff3333, #ff1111)**.
---
## Add a featured product
- Go to **Extensions** - **Extensions** - **Modules** - **Featured** - **Home Page**
- Click on **Edit** button
- Add the products 
---
## Theme options
- Go to **Extensions** - **Extensions** - **Themes** - **Default store theme**
- Click on **Edit** button
- Options:
    - Items per page - 24
    - List description character limit - 100
    - Image/Thumb sizes
---
## Remove **compare**
- Go to **Design** - **Theme Editor**
    1. From **product/search.twig** remove **button_compare** and Save.
    2. From **product/special.twig** remove **button_compare** and Save.
    3. From **product/category.twig** remove **button_compare** and Save.
    4. From **product/manufacturer_info.twig** remove **button_compare** and Save.
    5. From **product/product.twig** remove **button_compare** and Save.
    5. From **extension/module/featured.twig** remove **button_compare** and Save.
---
## Remove **returns**
- Go to **Design** - **Theme Editor**
    1. From **common/footer.twig** remove **returns** and Save.
---
## Have the main product image fill the width in the product page
- Open file **/catalog/view/javascript/bootstrap/css/bootstrap.min.css**
- Search for **.thumbnail>img**
- Add **width:100%** to it.
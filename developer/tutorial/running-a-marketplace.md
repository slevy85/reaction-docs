# Marketplace

View our marketplace feature roadmap and progress on our [github marketplace project](https://github.com/reactioncommerce/reaction/projects/9)

Participate in discussion and ask marketplace specific questions on our [marketplace gitter channel](https://gitter.im/reactioncommerce/marketplace)

## How to test drive the marketplace feature branch

### 0. Prerequisites
 - [Get your system ready for Reaction](https://docs.reactioncommerce.com/reaction-docs/master/requirements)
 - [Install the reaction-cli tool](https://docs.reactioncommerce.com/reaction-docs/master/installation)

### 1. Checkout or clone the marketplace branch from github
If you already have a development directory for Reaction Commerce setup, you can just checkout the `marketplace` branch. Make sure you `fetch` and `pull` to get the latest updates.

```sh
$ git checkout marketplace
$ git fetch
$ git pull
```

if you want to clone the `marketplace` branch have your public key setup in github

```
$ git clone -b marketplace git@github.com:reactioncommerce/reaction.git
```

If you don't have your public key uploaded to github, you can use https instead
```
$ git clone -b marketplace https://git@github.com/reactioncommerce/reaction.git
```

### 2. Setup default admin account info in settings.json
Copy the file `settings/dev.settings.json` to `settings/settings.json`. Add your desired username, password, and email address to the reaction section. You can set your SMTP string here as your MAIL_URL, but there's a better way to do that that we'll get to in step 3.

```
{
  "ROOT_URL": "",
  "MAIL_URL": "",
  "reaction": {
    "REACTION_USER": "username",
    "REACTION_AUTH": "password",
    "REACTION_EMAIL": "email@example.com"
  },
  "REACTION_LOG_LEVEL": "info",
  "public": {}
}
```

### 3. Setup email (and whatever else you need) in reaction.json
 This can be done by setting your SMTP username, password, host, and port in the `private/settings/reaction.json` file before starting the app. Copy the file from `private/settings/reaction.json.example` and fill out the `mail` section as well as any other sections you'd like.

If you were using Postmark to send mail, the mail section might look like this:

```
 "mail": {
    "user": "postmark-user-string",
    "password": "postmark-password-string",
    "host": "smtp.postmarkapp.com",
    "port": 587
},
```

### 4. Start Reaction
`$ reaction run`


### 5. Login as the Marketplace Owner
In your main browser window, login to the application using the `REACTION_EMAIL` and `REACTION_AUTH` you supplied in step 2.

![image](https://cloud.githubusercontent.com/assets/1203639/25508919/6d74bb2c-2b72-11e7-81ea-e60b7ad0391a.png)

### 6. Login as a Guest
In an incognito window or alternate browser, create a guest account. From the Sign In dropdown, click the `Register` link:
<img src="https://cloud.githubusercontent.com/assets/1203639/25509308/25b0db10-2b75-11e7-9baf-7de2cb014b64.png" width="50%">

Create a 2nd account by supplying an email and a password. If you want to have emails all go to the same address you can use an email like this `youremail+shop1@example.com`

Once you've registered you'll automatically be logged in.

### 7. As a Guest, visit your Profile page
Click the "Guest" dropdown tab next to the shopping cart where the Sign In dropdown was previously.
![image](https://cloud.githubusercontent.com/assets/1203639/25509608/75b216ae-2b77-11e7-8b03-d3d7b17320ea.png)

From the dropdown menu, click into your profile.
![image](https://cloud.githubusercontent.com/assets/1203639/25509705/240a0a7c-2b78-11e7-8525-5c753e54ef04.png)

### 8. Click the "Become A Seller" button
Scroll down towards the bottom of your profile and click the "Become a seller" button.
![image](https://cloud.githubusercontent.com/assets/1203639/25510168/55ac2e04-2b7b-11e7-845d-0d07c3b07205.png)

You should see a confirmation notification that "Your shop is now ready!"
![image](https://cloud.githubusercontent.com/assets/1203639/25510217/b1d1df9e-2b7b-11e7-9541-fb0407b14e9d.png)

### 9. You are granted additional functionality as a shop owner
![image](https://cloud.githubusercontent.com/assets/1203639/25510332/a14c29a8-2b7c-11e7-91e7-06accdee7f11.png)
There's a lot that just happened
You've just been granted a new Shop and admin access for that shop.

This grants you the ability to toggle "Edit Mode" on and off (starts on) which permits you to edit products, drag and drop order of images and products in your catalog, edit tags and more.

You also get access to edit your Shop Settings, view incoming orders, and create products.

The Reaction logo in the top right corner will toggle your admin dashboard panel on and off.


### 10. Customize your shop
Click on the "Shop Settings" link in your user dropdown.
![image](https://cloud.githubusercontent.com/assets/1203639/25510571/570a6b28-2b7e-11e7-8bb4-dde738002f97.png)
From here, you can set your shop name, email, a description, some keywords, your timezone, a Base Currency and your base unit of measure.

By clicking on the "Address" header towards the bottom, you can setup your shop's address as well.

### 11. Create Your First Product
#### Creating a product
![image](https://cloud.githubusercontent.com/assets/1203639/25550040/1e4ad5b0-2c33-11e7-8c0a-47786c819b24.png)  
Click the `+` plus button  in the admin header to create a new product  

#### Editing A Product
![image](https://cloud.githubusercontent.com/assets/1203639/25550342/8dcecc00-2c35-11e7-91a1-f74e68b1ad3d.png)
Check that you are in "Edit Mode" - this is the switch in the top-left of the screen. When you are in edit mode, you are viewing the product as an Admin and you can edit the fields of the product in place. Want to change the title? Just click the title and start typing.

When you make changes to any field of your product, they are saved immediately as **_unpublished changes_**. You don't have to click "save" at any point when editing a product in Reaction, but you also don't have to worry about customers seeing edits that aren't ready yet.

Go ahead and add a title and subtitle to your product, you can add a vendor and description if you like as well. You'll see as soon as you change a field that there is a gold "pencil" icon that appears. This icon indicates that you have unpublished changes on this field.

To publish your changes, you need to click the "Publish" button in the top right of the screen. Clicking publish will update your product to use the changes you just made to your product. Publishing changes to a product has no affect on the product's visibility, publishing changes only updates the version of your product that would be visible.

To make a product visible to the public, you need to click on the little "eye" icon to the left of the publish button. You can toggle a product's visiblity on and off with this icon. When the product is hidden, the product will show an eye icon with a slash through it. When the product is visible, the eye icon will not have a slash through it.

#### Products and Variants
A source of confusion for some is how Reaction's system of Products and Variants works. When you create your first product, you are essentially creating a shell product that can have many variants (and sub-variants, and sub-sub variants...)

Each product has at minimum, one variant. This variant is where the price, quantity, weight and other variables might live. This may be confusing if you have a product with only one variant, but it makes a lot of sense for products with multiple variants.

To edit your first variant, called "Label" by default, click the grey pencil icon in the corner of the variant. Worth noting that you have control over a variant's visibility independently of it's parent product or variant.    

![image](https://cloud.githubusercontent.com/assets/1203639/25550989/fff410f0-2c3b-11e7-8353-581cf4becc80.png)

Clicking the "Edit Variant" icon, will slide open the Edit Variant panel.

#### Edit Variant

![image](https://cloud.githubusercontent.com/assets/1203639/25551134/aff3b6c6-2c3d-11e7-94ba-737b7ad178f9.png)

# Express Install Profile

This is the working version porting the [Express Install Profile](https://www.drupal.org/project/express) used by the University of Colorado to Backdrop.

This is an install profile that needs to be placed in /core/profiles to be discovered during the install process.

```
composer create-project -s dev backdrop/backdrop
cd backdrop
composer install
ddev config 
```
Use the defults when prompted by ddev.

[Follow the steps to add Backdrop's version of Drush to DDEV](https://github.com/backdrop-contrib/bee/wiki/Using-bee-with-DDEV)
```
ddev start
mkdir profiles
cd profiles
git clone git@github.com:backdrop-contrib/express.git
```

Until we have scripts to add the Backdrop module dependencies declared the express.info, those modules should be added using `bee dl`. 
Unlike the Drupal 7 Install Profile where the dependencies are added to packaged download with `drush make`, Backdrop requires the
dependencies to be added with an additional step before the install profile is used.

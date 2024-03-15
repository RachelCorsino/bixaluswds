# Contribution Guidelines for Bixal Theme
### Please follow the guidelines bellow to set up your local environment to contribute to the Bixal USWDS theme

1. Ensure that you have completed the drupal standard installation. If you have not, see https://github.com/rayestrada/drupalstandard for install instructions.

1. `cd` into web/themes directory and create a new directory named `custom`. `cd` into the newly created custom folder.

1. If you have not already, create a forked repository from the bixaluswds repo. See https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo for instructions on how to fork the repository. Once you have a forked repository, clone it within your `custom` folder.

1. `cd` back to your drupalstandard directory and initialize child theme using drupal theme generate function.

    Determine what theme name you want to use in this example we are using my_new_theme.
    ```
    lando php web/core/scripts/drupal generate-theme --starterkit starter_theme my_new_theme --path themes/custom

    lando drush cr
    ```

1. Open your custom theme info file and remove the following lines
    ```
    hidden: true
    starterkit: true
    ```

1. Install the theme dependencies

    Run the following commands in your terminal to install twig_tweak, twig_field_value, uswds_templates, block_content_template, and focal_point

    ```
    lando composer require 'drupal/twig_tweak:^3.3'
    lando drush en twig_tweak

    lando composer require 'drupal/twig_field_value:^2.0' lando drush en twig_field_value

    Lando composer require 'drupal/uswds_templates:3.0.x-dev@dev' 
    lando drush en uswds_templates 

    lando composer require 'drupal/block_content_template:^1.5' 
    lando drush en block_content_template

    lando composer require 'drupal/focal_point:^2.0'
    lando drush en focal_point
    ```

1. `cd` into your custom theme (web/themes/custom/bixaluswds) and make sure you are within the dev branch. Here you can checkout the branch you want to contribute to or create a new branch

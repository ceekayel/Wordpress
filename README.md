##Basic steps for how I created this

* Following this guide: [Composer Project Recipe: Site Stack](http://composer.rarst.net/recipe/site-stack)

* Use this tip: [Composer Recipe: Enable Wordpress Paths Pattern](http://composer.rarst.net/recipe/paths-control) to enable WordPress directory layout when installing plugins and themes

    ```
      php composer.phar require "composer/installers"
    ```

* create artifacts

    ``` 
      php composer.phar install --prefer-dist 
    ```

* This is optional (more options suggested below), but is very common in practice [enable multiple themes](https://wordpress.org/plugins/jonradio-multiple-themes/installation/)

    ```
      php composer.phar require "wpackagist-plugin/jonradio-multiple-themes"
    ```

##How to use this to create a new project

1. Copy composer.json and (optionally) composer.phar into new folder 

    * **caveat**: you may have already, or could install, the phar file. For OSX, this would be something like

        ```
          cp composer.phar /usr/local/bin/composer
        ```

2. edit project and contact details in the json file as desired 
3. run one of the following commands
    * if you do not have the composer script installed system-wide
    
        ``` 
          php composer.phar install --prefer-dist 
        ```
    * if you have the composer script installed you can do the short-cut version
    
        ``` 
          composer install --prefer-dist 
        ```


##Optional next steps

* **Bootstrap** (requires a theme, as appears in the suggestion when executing this command)

    ```
      composer require "components/bootstrap"
    ```

* **Themes and plugins:** if you have locally available themes or plugins (such as paid third-party sources or custom ones) [here is how to do it](http://tech.vg.no/2014/11/25/using-local-packages-as-composer-dependencies)

    ```
      "repositories": [ 
        {...},
        {
          "type": "vcs",
          "url": "../changeMeLocalUrlForPluginOrTheme"
        }
      ]
    ```
* **Custom Themes** Consider creating a child theme if you're modifying an existing one http://codex.wordpress.org/Child_Themes
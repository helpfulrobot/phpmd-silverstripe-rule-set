## PHPMD rule set for SilverStripe projects

Some rules in the default configuration of PHPMD aren't ideal for SilverStripe projects. This repo is offering an adjusted set of rules to provide you with noise-free PHP mess detection messages.

### Set up

1. Install PHPMD globally:

```
composer global require "phpmd/phpmd"
```

2. Clone this repo wherever you like to, for example:

```
git clone git@github.com:spekulatius/phpmd-silverstripe-rule-set.git ~/.config/phpmd-silverstripe-rule-set
```


### How to use this?

To run the mess detector you need to define the rules you like to apply. The following example applies all rule sets:
  ```
  ~/.composer/vendor/phpmd/phpmd/src/bin/phpmd /path/to/your/SilverStripe/Project/YourFile.php text ~/.config/phpmd-silverstripe-rule-set/cleancode.xml ~/.config/phpmd-silverstripe-rule-set/codesize.xml ~/.config/phpmd-silverstripe-rule-set/controversial.xml ~/.config/phpmd-silverstripe-rule-set/design.xml ~/.config/phpmd-silverstripe-rule-set/naming.xml ~/.config/phpmd-silverstripe-rule-set/unusedcode.xml
  ```

### Configuration for Sublime`s PHPCS module

If you'd like to use this in conjunction with Sublime`s PHPCS package you need to add this configuration:

```
    // PHP Mess Detector settings

    // Execute phpmdse
    "phpmd_run": true,

    // Execute the phpmd on file save
    "phpmd_command_on_save": true,

    // It seems python/sublime cannot always find the phpmd application
    // If empty, then use PATH version of phpmd, else use the set value
    "phpmd_executable_path": "~/.composer/vendor/phpmd/phpmd/src/bin/phpmd",

    // Additional arguments you can specify into the application
    //
    // Example:
    // {
    //     "codesize,unusedcode"
    // }
    "phpmd_additional_args": {
        "~/.config/phpmd-silverstripe-rule-set/cleancode.xml": "",
        "~/.config/phpmd-silverstripe-rule-set/codesize.xml": "",
        "~/.config/phpmd-silverstripe-rule-set/controversial.xml": "",
        "~/.config/phpmd-silverstripe-rule-set/design.xml": "",
        "~/.config/phpmd-silverstripe-rule-set/naming.xml": "",
        "~/.config/phpmd-silverstripe-rule-set/unusedcode.xml": ""
    }
```

### Troubleshooting

If PHPMD doesn't seem to work open the console with ```Ctrl + ` ``` and see what is happening on save. If you get an ```FileNotFoundError: [Errno 2] No such file or directory: '~/.composer/vendor/phpmd/phpmd/src/bin/phpmd'``` you need to adjust the "~" to your actual home directory.


### State

This repo is and probably will be "in work" for a long time. I'm happy to merge pull requests.

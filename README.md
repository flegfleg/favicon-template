# favicon-template (with wordpress header hook)

## Create the icons

Open sketch file, place your icons. 

run 

    $ convert 16x16.png 32x32.png 48x48.png 64x64.png 128x128.png favicon.ico

(you can delete the following 16x16.png 32x32.png 48x48.png 64x64.png 128x128.png )

## Copy them into your theme directory 

Here: /assets/images/favicon/

## Add hook

Add hook to your themes functions file

    /**
    Add common favicons 
    */
    function fleg_do_favicon() { ?>
    <link rel="shortcut icon" href="<?php echo bloginfo('stylesheet_directory') ?>/assets/images/favicon/favicon.ico" >
    <link rel="icon" sizes="16x16 24x24 32x32 48x48 64x64" href="<?php echo bloginfo('stylesheet_directory'); ?>/assets/images/favicon/favicon.ico" >
    <?php // Microsoft ?>
    <meta name="msapplication-TileColor" content="#FFFFFF" />
    <link rel="msapplication-TileImage" sizes="144x144" href="<?php echo bloginfo('stylesheet_directory'); ?>/assets/images/favicon/mstile-144.png" />
    <?php // apple ?>
    <link rel="apple-touch-icon" sizes="152x152" href="<?php echo bloginfo('stylesheet_directory'); ?>/assets/images/favicon/apple-touch-icon-152x152.png" />

    <?php }
    add_action('wp_head', 'fleg_do_favicon');

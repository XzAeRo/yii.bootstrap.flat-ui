Bootstrap Extension + Flat UI Theme for Yii
=======

Bootstrap Extension + Flat UI Theme for Yii is licensed under a Creative Commons Attribution 3.0 Unported (CC BY 3.0)  (http://creativecommons.org/licenses/by/3.0/) and MIT License - http://opensource.org/licenses/mit-license.html. 

You are allowed to use these elements anywhere you want, however I’ll highly appreciate if you will link to this repo or my github user.

## Links:

+ [Download latest version](https://github.com/XzAeRo/yii.bootstrap.flat-ui/archive/master.zip)
+ [Flat UI Free](http://designmodo.github.com/Flat-UI/)
+ [Yii-Bootstrap Extension](http://www.cniska.net/yii-bootstrap/)
+ [Yii Framework](http://www.yiiframework.com/)

## Changelog

**[initial release] v0.9 (compared to the Yii-Bootstrap Extension)**
+ [new] Added Flat Ui Free css, js, images and .less files.
+ [new] Registration of the files in the Yii-Bootstrap extension.
+ [fix] Added 'data-toggle' attribute with fixed value to checkbox element.

## TO-DO
+ Allow 'checkbox' and 'switch' values in 'data-toggle' for checkbox elements.
+ Add IE html5 compatibility.
+ Installer.

## Author

**Victor Gonzalez**
+ Google+: [https://plus.google.com/112782856974100248968](https://plus.google.com/112782856974100248968)
+ Facebook: [https://www.facebook.com/xzaero](https://www.facebook.com/xzaero)

## Introduction
Bootstrap Extension + Flat UI Theme for Yii is a mix between the [Yii-Bootstrap Extension](http://www.cniska.net/yii-bootstrap/), wich includes the Yii definitions for the html elements used in the [Twitter Bootstrap UI Framework](http://twitter.github.io/bootstrap/), and the [Flat UI Free Framework](http://designmodo.github.com/Flat-UI/), wich is a extension/theme for the Bootstrap framework.

I'm releasing this as a whole package to prevent confussion in the installing process.


## Requirements

**Yii Framework**

First of all, you need you have installed in your server the [Yii Framework](http://www.yiiframework.com/). It's higly recommended that you have the latest version installed, since the development of this extension will try to keep up to the latest versions of this frameworks.

Also, you need to have access to the server files (this can be done via ftp or ssh), since you have to upload files manually.

## Installation

Once you have [downloaded the latest version](https://github.com/XzAeRo/yii.bootstrap.flat-ui/archive/master.zip), unzip the extension under `protected/extensions/bootstrap`. The folder structure should be something like this:

	webroot/
		protected/
			extensions/
				bootstrap/
					assets/
					components/
					form/
					gii/
					theme/
					widgets/


Now you need to copy the `theme/` folder to themes folder and rename it to 'bootstrap'. The folder structure should be like this :

	webroot/
		protected/
		theme/
			bootstrap/
				css/
				views/


Now that you have everything in the right place, we need to tell Yii that we have a new extension and a new theme. To do this, we need to edit the Yii config file, wich can be found (most likely), under `webroot/protected/config/main.php`.

Under the main Web application configuration array, you need to add the following lines like this:

`webroot/protected/config/main.php`

	<?php
	// Define a path alias for the Bootstrap extension as it's used internally.
	// In this example we assume that you unzipped the extension under protected/extensions.
	Yii::setPathOfAlias('bootstrap', dirname(__FILE__).'/../extensions/bootstrap/');
	 
	return array(
	    'theme'=>'bootstrap',
	    'modules'=>array(
	        'gii'=>array(
	            'generatorPaths'=>array(
	                'bootstrap.gii',
	            ),
	        ),
	    ),
	    'components'=>array(
	        'bootstrap'=>array(
	            'class'=>'bootstrap.components.Bootstrap',
	        ),
	    ),
	);


Once you have done this, just refresh your Yii website and you should see the whole Flat UI theme in his full beauty.

## Troubleshooting

+ **Theme not updating after installation:** check that you followed every step in the installation process, and verify the folder structure for the extension and the theme.
+ **I made some changes in the extension css, or javascript, and it's not being updated in the live website:** delete everything under the webroot assets folder `webroot/assets`, and then refresh you website in the browser.
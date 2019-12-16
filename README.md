# ion-floating-menu

Material UI-like Floating Action Button and Menu for Ionic applications.

This version is a fork from the original plugin and includes a root scope event listner to trigger the menu closing. To close all open floating menus you can call:

`$rootScope.$broadcast('floating-menu:close-all')`

## Features

- Button similar to the Material UI Floating Action Button
- Menu similar to the Material UI Menu

## Setup

#### Install

`bower install https://github.com/rodrigovillaca/ion-floating-menu.git`

#### JS/CSS Imports (index.html)

Include the following file imports in your index.html (the example assumes ./lib/ion-floating-menu folder):

    <link href="lib/ion-floating-menu/dist/ion-floating-menu.css" rel="stylesheet" type="text/css"/>
        ...
    <script src="lib/ion-floating-menu/dist/ion-floating-menu.js" type="text/javascript"></script>

#### Angular Dependency (app.js)

Add `ion-floating-menu` as a module dependency of your angular module.

angular.module('MyApp', ['ionic', 'ion-floating-menu'])
...

## Usage: ionic-floating-button

![Alt ion-floating-button](/doc/ion-floating-button.png?raw=true)

Add the `ion-floating-button` directive in your template.

Important: put it before and outside the `ion-content` node:

    <ion-floating-button click="myEvent()" has-footer="false" button-color="#2AC9AA" icon="ion-plus" icon-color="#fff">
    </ion-floating-button>

    <ion-content>
        ...

where `myEvent()` is trigger when you tap or click.

#### Config

- **click**: event expression
- **button-color**: CSS Color for the button (`#2AC9AA` by default)
- **button-class**: CSS Class to apply your style to the button (alternative to `button-color`)
- **icon**: ionic icon (`ion-plus` by default; note that the `icon` class is already defined)
- **icon-color**: CSS Color for the icon (`#fff` by default)
- **has-footer**: if the template has a footer, so it fixes the position (`false` by default)
- **bottom**: CSS value in pixel to change the distance from the bottom, e.g. 40px. If has-footer is true, the value does not apply. By default is 20px if has-footer = false and 60px if has-footer = true
- **is-centered**: `true` to center the button
- **text**: if you want to attach a lable to the button
- **text-class**: CSS Class for the button. Note: add !important to the CSS statements if they are not applied correctly.

## Usage: ion-floating-menu

![Alt ion-floating-menu](/doc/ion-floating-menu.png)
![Alt ion-floating-menu](/doc/ion-floating-menu-2.png)

Add the `ion-floating-menu` directive in your template.

Important put it before `ion-content`.

    <ion-floating-menu>
        <ion-floating-item icon="ion-camera" click="myEvent()"></ion-floating-item>
        <ion-floating-item icon="ion-person" click="myEvent()"></ion-floating-item>
    </ion-floating-menu>

where `myEvent()` is trigger when you tap or click.

#### Config

ion-floating-menu:

- **menu-color**: CSS Color for the button (`#2AC9AA` by default)
- **menu-icon**: ionic icon (`ion-plus` by default; note that the `icon` class is already defined)
- **menu-icon-color**: CSS Color for the icon (`#fff` by default)
- **menu-open-color**: CSS Color for the button (`#2AC9AA` by default)
- **menu-open-icon**: ionic icon (`ion-minus` by default; note that the `icon` class is already defined)
- **menu-open-icon-color**: CSS Color for the icon (`#fff` by default)
- **has-footer**: if the template has a footer, so it fixes the position (`false` by default)
- **bottom**: CSS value in pixel to change the distance from the bottom, e.g. 40px. If has-footer is true, the value does not apply. By default is 20px if has-footer = false and 60px if has-footer = true
- **backdrop**: if true the Ionic backdrop is applied as the menu open (see demo/menu-with-backdrop.html).

ion-floating-item:

- **click**: event expression (required)
- **icon**: ionic icon (required)
- **text**: if you want to attach a lable to the button
- **text-class**: CSS Class for the button. Note: add !important to the CSS statements if they are not applied correctly.
- **button-color**: CSS Color for the button (`#2AC9AA` by default)
- **button-class**: CSS Class to apply your style to the button (alternative to `button-color`)
- **icon-color**: CSS Color for the icon (`#fff` by default)
- **icon-image-path**: If you want to use an icon image rather than a class, you can specify the image path here
- **icon-image-class**: CSS Class to apply your style to the icon image

#### Events

ion-floating-menu:

- **floating-menu:open**: Triggered when the menu opens
- **floating-menu:close**: Triggered when the menu closes

For example

    $scope.$on('floating-menu:open', function(){
                        ...
    });

## Questions?

If you have any question or remark, you can either:

- posting a comment on this site,
- send me an email: ndg@pregiotek.com
- report it on the [Github page](https://github.com/pregiotek/ion-floating-menu)

Have fun!

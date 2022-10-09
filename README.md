# Design Tokens Example
This is a super simple example on how to use Design Tokens as a source of truth for better Design <> Development collaboration.

This process is awesome and very important as it helps brands, products and teams maintain consistency of all their brand design styles in a **cross-platform** and **cross-language** way. 
This means that the design styles defined by designers in Figma will be converted into coding styles in any language/technology a developer is using to build an application, improving the workflow and communication to ship or release features with more consistency and speed.

## Step 1 - Exporting from Figma
First, you need to generate a .json file with all the values of your Design System. This can be done using the Figma Tokens plugin, which allows to generate the .json file with all design system data as in the code below:

#### .json file generated with the Figma Tokens plugin
```
{
  "global": {
    "colors": {
      "red500": {
        "value": "#A91B1B",
        "type": "color"
      },
      "green500": {
        "value": "#12A43B",
        "type": "color"
      },
      "blue500": {
        "value": "#122BAD",
        "type": "color"
      },
      "yellow500": {
        "value": "#F2CD0B",
        "type": "color"
      }
    }
  }
}
```


## Step 2 - Converting the data in the .json file in a way any platform or language to consume
Using **Style Dictionary**, a build system developed by Amazon, we can export the rules in the .json file to all the places we need them - iOS, Android, CSS, JS, HTML, style documentation, or anything you can think of. 

```
css/variables
scss/variables
less/variables
compose/object
android/resources
ios-swift/class.swift
ios-swift/enum.swift
flutter/class.dart
```

In this example I'll keep it simple and will only be exporting to SCSS and CSS variables.

The configuration has been set up in the **config.json** file and by running `npm run build` the files will be generated and exported in the `/out` folder.

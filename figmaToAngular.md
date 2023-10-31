![A Back to Readme](media/arrow-circle-left.svg)

# INDEX: How to Convert Figma to Angular

**Overview**

The objective of this demonstration, is to convert a Figma frame, that represents a web page, to an Angular component that uses Angular Material. We will also explore how to integrate with the code behind (component.ts).

Building Blocks

Figma, Anima, VS Code

## Here is the workflow for the conversion process:

[Workflow Part 1: Update Angular Project](figmaToAngular-p1.md)

[Workflow Part 2: Update Angular Library](figmaToAngular-p2.md)

[Workflow Part 3: Update Angular Component](figmaToAngular-p3.md)

The conversion process comes with an object model

[Conversion Object Model](figmaToAngular-model.md)

The conversion process has a group of associated control types

[Control Types & Conversion](figmaToAngular-control-types.md)

Each control type has an associated implementation. The documentation for most of the control types comes from the Angular Material documentation.

Here is an example using the customer’s name field on the ahs.html page. This is part of the conversion model.

```
{
  "enabled": true,
  "controlType": "mat-text-field",
  "className": "ahs-customer-name",
  "label": "Customer Name",
  "placeholder": "Enter customer name",
  "type": "text",
  "value": "",
  "required": "false",
  "formControl": ""
},
```

Here you will find the properties that are used in the implementation. From this you will determine that the control type is the 'mat-text-field'. Also, you will find the label, “placeholder” and type of the html input control.

Note: that the type can be “text”, “number”, or “email”.

Now, that you know the control type is a mat-text-field, you can replace the div in the exported Anima html file with the Angular Material implementation using the properties provided in the model. Search, for the 'div' in the ahs.html file for: `class="ahs-customer-name"`

For more information how to convert using the control type, go to the [figmaToAngular-control-types](figmaToAngular-control-types.md) documentation.

[Exercise: Convert customer name in the ahs page from a div to an Angular Material control](figmaToAngular-exercise.md)

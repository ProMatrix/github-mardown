[![Back to the Beginning](media/arrow-circle-left.svg)](figmaToAngular.md)

# Workflow Part 2: Update Angular Library

The focus for this part is to copy and modify the files for one Figma page. The page is the "ahs.html" in the "ahs-lib" Angular project.

**Note:** It is necessary to repeat this part of the workflow, for every Figma page.

Starting with the page: ahs.html

Step 1: copy: anima/ahs.html to projects/ahs/ahs-lib/src/lib/ahs.html.

Also copy: anima/ahs.css to projects/ahs/ahs-lib/src/lib/ahs.css.

Step 2: remove all the html before and after the div with the class: "container-center-horizontal". This html is not necessary when inside an Angular component.

Note: After Step 2, you will be able to build, and run the app for the Account Activity History. The page will display using divs instead of real controls.

Step 3: replace the div for the controls, starting with the customer name.  Use the control-type to determine the implementation details.

The control type for the customer name is: "*mat-text-field"*

The html update for the customer name should look something like this:

**Replace:**

`<div class="ahs-customer-name"><p class="textfield roboto-normal-gravel-16px">&nbsp;&nbsp;&nbsp;&nbsp;Customer Name</p></div>`

**With:**

`<mat-form-field class="ahs-customer-name"><mat-label>Customer Name</mat-label><input matInput type="text" [required]="false" placeholder="Enter customer name" value="" ></mat-form-field>`

Step 4: update the css class associated with the control. In this case, update the css class with the properties listed in the conversion model for the css class "ahs-customer-name".

The css update for the customer name should look something like this:

Replace:

```
.ahs .ahs-customer-name {
  background-color: var(--cultured-pearl);
  border-bottom-style: solid;
  border-bottom-width: 1px;
  border-color: var(--mountain-mist);
  border-radius: 3px;
  height: 56px;
  left: 50px;
  overflow: hidden;
  position: absolute;
  top: 40px;
  width: 300px;
}
```

**With:**

```
.ahs .ahs-customer-name {
  left: 50px;
  overflow: hidden;
  position: absolute;
  top: 40px;
  width: 300px;
  height: auto;
  font-family: Roboto,
 Helvetica;
}
```

**Note:** It is necessary to repeat this part of the workflow, for every control on the page.

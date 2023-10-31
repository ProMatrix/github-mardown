[![Back to the Beginning](media/arrow-circle-left.svg)](figmaToAngular.md)

# List of Control Types using Angular Material

Overview: The information following details what to replace from the original exported Anima html file, to become an Angular html file using Angular Material controls. Once you determine the controls being replaces, you can extract all the properties of the control from the conversion model. This information, along with the Angular Material documentation should serve as a guide to the conversion.

## mat-text-field

[Angular Material: Input Overview](https://material.angular.io/components/input/overview)

**Replace:**

`<div class="ahs-customer-name"><p class="textfield roboto-normal-gravel-16px">&nbsp;&nbsp;&nbsp;&nbsp;Customer Name</p></div>`

**With:**

`<mat-form-field class="ahs-customer-name"><mat-label>Customer Name</mat-label><input matInput type="text" [required]="false" placeholder="Enter customer name" value="" ></mat-form-field>`

Notice that the class name is the same name

## mat-select

## mat-button

## mat-date-range-picker

## mat-slide-toggle

## mat-button-toggle-group

## copyright-component

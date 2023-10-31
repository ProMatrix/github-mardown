[![Back to the Beginning](media/arrow-circle-left.svg)](figmaToAngular.md)

# Conversion Object Model

Here is the object model for the conversion settings and is patterned for automation. You will find in the conversion model, all the controls that will be converted to using Angular Material.

```
{
  "projectPages": [
    {
      "name": "ahs",
      "htmlFile": "ahs.html",
      "cssFile": "ahs.css",
      "scssFile": "ahs.scss",
      "cssImagePath": "../img",
      "componentFolder": "lib",
      "angularControls": [
        {
          "enabled": true,
          "controlType": "mat-text-field",
          "className": "ahs-customer-name",
          "label": "Customer Name",
          "placeholder": "Enter customer name",
          "type": "text",
          "value": "",
          "required": "false",
          "formControl": "",
          "removedCssProperties": ["background-color", "border-bottom-style", "border-bottom-width", "border-color",
          "border-radius", "height"],
          "addedCssProperties": ["height: auto", "font-family: Roboto, Helvetica"]
        },
        {
          "enabled": true,
          "controlType": "mat-button-toggle-group",
          "className": "ahs-search-mode",
          "ngModel": "searchMode",
          "vertical": "false",
          "childControls": [
            {
              "controlType": "mat-button-toggle",
              "label": "Day by Day"
            },
            {
              "controlType": "mat-button-toggle",
              "label": "Individual Location"
            }
          ],
          "removedCssProperties": ["height"],
          "addedCssProperties": ["height: auto"]

        },      
        {
          "enabled": true,
          "controlType": "mat-button",
          "className": "ahs-internal-search",
          "label": "Internal Search",
          "click": "onclickInternalSearch('Thank you for clicking me!')",
          "removedCssProperties": ["background-color"],
          "addedCssProperties": ["font-family: Roboto, Helvetica", "font-size: 16px"]
        },
        {
          "enabled": true,
          "controlType": "mat-select",
          "className": "ahs-detail-mode",
          "label": "Detail Mode",
          "required": "",
          "formControl": "",
          "options": "<mat-option value='all'>All</mat-option><mat-option value='first-5'>First Five</mat-option><mat-option value='last-5'>Last 5</mat-option>",
          "removedCssProperties": ["align-items",
          "background-color", "border-bottom-style", "border-bottom-width", "border-color",
          "border-radius", "display", "height", "overflow", "padding"],
          "addedCssProperties": ["height: auto"]
        },
        {
          "enabled": true,
          "controlType": "mat-select",
          "className": "ahs-date-range-select",
          "label": "Date Range",
          "required": "",
          "formControl": "",
          "options": "<mat-option value='all'>Last Week</mat-option><mat-option value='first-5'>Last Month</mat-option><mat-option value='last-5'>Last Year</mat-option>",
          "removedCssProperties": ["align-items",
          "background-color", "border-bottom-style", "border-bottom-width", "border-color",
          "border-radius", "display", "height", "overflow", "padding"],
          "addedCssProperties": ["height: auto"]
        },
        {
          "enabled": true,
          "controlType": "mat-date-range-picker",
          "className": "ahs-calendar-date-range",
          "label": "Enter a date range",
          "hint": "Removed hint for now",
          "ngName": "rangePicker",
          "removedCssProperties": ["align-items",
          "background-color", "border-bottom-style", "border-bottom-width", "border-color",
          "border-radius", "display", "height", "overflow", "padding"],
          "addedCssProperties": ["height: auto"]
        },
        {
          "enabled": true,
          "controlType": "mat-slide-toggle",
          "className": "ahs-use-customer-id",
          "label": "Use customer ID instead of name",
          "labelPosition": "before",
          "ngModel": "isUsingCustomerId",
          "removedCssProperties": ["left"],
          "addedCssProperties": ["left: 38px"]
        },
        {
          "enabled": true,
          "controlType": "mat-slide-toggle",
          "className": "ahs-include-balance",
          "label": "Include Balance",
          "labelPosition": "before",
          "ngModel": "isIncludingBalance",
          "removedCssProperties": ["left"],
          "addedCssProperties": ["left: 100px"]
        },
        {
          "enabled": true,
          "controlType": "mat-select",
          "className": "ahs-interface-select",
          "label": "Interface",
          "required": "",
          "formControl": "",
          "options": "<mat-option value='all'>Last Week</mat-option><mat-option value='first-5'>Last Month</mat-option><mat-option value='last-5'>Last Year</mat-option>",
          "removedCssProperties": ["align-items",
          "background-color", "border-bottom-style", "border-bottom-width", "border-color",
          "border-radius", "display", "height", "overflow", "padding"],
          "addedCssProperties": ["height: auto"]
        },
        {
          "enabled": true,
          "controlType": "mat-select",
          "className": "ahs-show-id-select",
          "label": "Show IDD",
          "required": "",
          "formControl": "",
          "options": "<mat-option value='all'>Last Week</mat-option><mat-option value='first-5'>Last Month</mat-option><mat-option value='last-5'>Last Year</mat-option>",
          "removedCssProperties": ["align-items",
          "background-color", "border-bottom-style", "border-bottom-width", "border-color",
          "border-radius", "display", "height", "overflow", "padding"],
          "addedCssProperties": ["height: auto"]
        },
        {
          "enabled": true,
          "controlType": "mat-select",
          "className": "ahs-bill-pay-select",
          "label": "Show Bill Pay Items",
          "required": "",
          "formControl": "",
          "options": "<mat-option value='all'>Last Week</mat-option><mat-option value='first-5'>Last Month</mat-option><mat-option value='last-5'>Last Year</mat-option>",
          "removedCssProperties": ["align-items",
          "background-color", "border-bottom-style", "border-bottom-width", "border-color",
          "border-radius", "display", "height", "overflow", "padding"],
          "addedCssProperties": ["height: auto"]
        },
        {
          "enabled": true,
          "controlType": "mat-select",
          "className": "ahs-credit-card-select",
          "label": "Credit Card Activity",
          "required": "",
          "formControl": "",
          "options": "<mat-option value='all'>Last Week</mat-option><mat-option value='first-5'>Last Month</mat-option><mat-option value='last-5'>Last Year</mat-option>",
          "removedCssProperties": ["align-items",
          "background-color", "border-bottom-style", "border-bottom-width", "border-color",
          "border-radius", "display", "height", "overflow", "padding"],
          "addedCssProperties": ["height: auto"]
        },
        {
          "enabled": true,
          "controlType": "mat-text-field",
          "className": "ahs-search-deposit-id",
          "label": "Search for Deposit ID",
          "placeholder": "Enter a deposit ID",
          "type": "text",
          "value": "",
          "required": "false",
          "formControl": "",
          "removedCssProperties": ["background-color", "border-bottom-style", "border-bottom-width", "border-color",
          "border-radius", "height"],
          "addedCssProperties": ["height: auto", "font-family: Roboto, Helvetica"]
        },
        {
          "enabled": true,
          "controlType": "mat-button",
          "className": "ahs-view-credit-card",
          "label": "View",
          "click": "onclickInternalSearch('Once is enough... Please stop clicking me!')",
          "removedCssProperties": ["background-color"],
          "addedCssProperties": ["font-family: Roboto, Helvetica", "font-size: 16px"]
        },
        {
          "enabled": true,
          "controlType": "mat-slide-toggle",
          "className": "ahs-show-grid",
          "label": "Grid",
          "labelPosition": "after",
          "ngModel": "isShowingGrid"
        },  
        {
          "enabled": true,
          "controlType": "copyright-component",
          "className": "ahs-copyright-component"
        }

      ],
      "editsAndAdditions": [
        {
          "enabled": true,
          "controlType": "add-raw-html",
          "className": "layout-grid",
          "addition": "*ngIf='isShowingGrid'"
        },
        {
          "enabled": true,
          "controlType": "add-a-class",
          "className": "layout-grid-container",
          "addition": "fade-in"
        } 
      ]
    }
  ]
}
```

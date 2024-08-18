# Bootstrap5 Dual Listbox
Bootstrap5 Dual Listbox is a responsive dual listbox widget optimized for Bootstrap 5. Works on all modern browsers and on touch devices.

Adapted from [bootstrap-duallistbox](https://github.com/istvan-ujjmeszaros/bootstrap-duallistbox) by Istvan Ujj-Meszaros.
Check [here](http://florianraabe.github.io/bootstrap5-duallistbox) for a demo.

## Usage

1. Download the latest release from the [releases page](https://github.com/florianraabe/bootstrap5-duallistbox/releases).

2. Include **jQuery** and **Bootstrap**:

See [bootstrap manual](https://getbootstrap.com/docs/5.0/getting-started/introduction/).

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">
<script src="https://code.jquery.com/jquery-3.7.1.slim.min.js" integrity="sha256-kmHvs0B+OpCW5GVHUNjv9rOmY0IvSIRcf7zGUDTDQM8=" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>
```

3. Include plugin's code:

```html
<script src="jquery.bootstrap5-duallistbox.min.js"></script>
```

4. Call the plugin:

```javascript
$("#element").bootstrapDualListbox({
    // see next for specifications
});
```

## Specifications

### Initialization parameters object

When calling `$("#element").bootstrapDualListbox()` you can pass a parameters object with zero or more of the following:

- `filterTextClear`, defaults to `'show all'`, is the text for the "Show All" button.
- `filterPlaceHolder`, defaults to `'Filter'`, is the placeholder for the `input` element for filtering elements.
- `moveSelectedLabel`, defaults to `'Move selected'`, is the label for the "Move Selected" button.
- `moveAllLabel`, defaults to `'Move all'`, is the label for the "Move All" button.
- `removeSelectedLabel`, defaults to `'Remove selected'`, is the label for the "Remove Selected" button.
- `removeAllLabel`, defaults to `'Remove all'`, is the label for the "Remove All" button.
- `moveOnSelect`, defaults to `true`, determines whether to move `option`s upon selection. This option is forced to `true` on the Android browser.
- `moveOnDoubleClick`, defaults to `true`, determines whether to move `option`s upon double click. This option is not used on the Android browser.
- `preserveSelectionOnMove`, can be`'all'` (for selecting both moved elements and the already selected ones in the target list) or `'moved'` (for selecting moved elements only); defaults to `false`.
- `selectedListLabel`, defaults to `false`, can be a `string` specifying the name of the selected list.
- `nonSelectedListLabel`, defaults to `false`, can be a `string` specifying the name of the non selected list.
- `helperSelectNamePostfix`, defaults to `'_helper'`. The added `select`s will have the same name as the original one, concatenated with this `string` and `1` (for the non selected list, e.g. `element_helper1`) or `2` (for the selected list, e.g. `element_helper2`).
- `selectorMinimalHeight`, defaults to `100`, represents the minimal height of the generated dual listbox.
- `showFilterInputs`, defaults to `true`, whether to show filter inputs.
- `nonSelectedFilter`, defaults to the empty string `''`, initializes the dual listbox with a filter for the non selected elements. This is applied only if `showFilterInputs` is set to `true`.
- `selectedFilter`, defaults to the empty string `''`, initializes the dual listbox with a filter for the selected elements. This is applied only if `showFilterInputs` is set to `true`.
- `infoText`, defaults to `'Showing all {0}'`, determines which `string` format to use when all options are visible. Set this to `false` to hide this information. Remember to insert the `{0}` placeholder.
- `infoTextFiltered`, defaults to `'Filtered {0} from {1}'`, determines which element format to use when some element is filtered. Remember to insert the `{0}` and `{1} `placeholders.
- `infoTextEmpty`, defaults to `'Empty list'`, determines the `string` to use when there are no options in the list.
- `filterOnValues`, defaults to `false`, set this to `true` to filter the `option`s according to their `value`s and not their HTML contents.

### Methods

You can modify the behavior and aspect of the dual listbox by calling its methods, all of which accept a `value` and a `refresh` option. The `value` determines the new parameter value, while `refresh` (optional, defaults to `false`) tells whether to update the plugin UI or not.

To call methods on the dual listbox instance, use the following syntax:

```javascript
$(selector).bootstrapDualListbox(methodName, parameter);
```

**Note**: when making multiple chained calls to the plugin, set `refresh` to `true` to the last call only, in order to make a unique UI change; alternatively, you can also call the `refresh` method as your last one.

Here are the available methods:

- `setFilterTextClear(value, refresh)` to change the `filterTextClear` parameter.
- `setFilterPlaceHolder(value, refresh)` to change the `filterPlaceHolder` parameter.
- `setMoveSelectedLabel(value, refresh)` to change the `moveSelectedLabel` parameter.
- `setMoveAllLabel(value, refresh)` to change the `moveAllLabel` parameter.
- `setRemoveSelectedLabel(value, refresh)` to change the `removeSelectedLabel` parameter.
- `setRemoveAllLabel(value, refresh)` to change the `removeAllLabel` parameter.
- `setMoveOnSelect(value, refresh)` to change the `moveOnSelect` parameter.
- `setMoveOnDoubleClick(value, refresh)` to change the `moveOnDoubleClick` parameter.
- `setPreserveSelectionOnMove(value, refresh)` to change the `preserveSelectionOnMove` parameter.
- `setSelectedListLabel(value, refresh)` to change the `selectedListLabel` parameter.
- `setNonSelectedListLabel(value, refresh)` to change the `nonSelectedListLabel` parameter.
- `setHelperSelectNamePostfix(value, refresh)` to change the `helperSelectNamePostfix` parameter.
- `setSelectOrMinimalHeight(value, refresh)` to change the `selectorMinimalHeight` parameter.
- `setShowFilterInputs(value, refresh)` to change the `showFilterInputs` parameter.
- `setNonSelectedFilter(value, refresh)` to change the `nonSelectedFilter` parameter.
- `setSelectedFilter(value, refresh)` to change the `selectedFilter` parameter.
- `setInfoText(value, refresh)` to change the `infoText` parameter.
- `setInfoTextFiltered(value, refresh)` to change the `infoTextFiltered` parameter.
- `setInfoTextEmpty(value, refresh)` to change the `infoTextEmpty` parameter.
- `setFilterOnValues(value, refresh)` to change the `filterOnValues` parameter.

Furthermore, you can call:

- `refresh()` or `trigger` the `bootstrapDualListbox.refresh` event to update the plugin element UI.
- `destroy()` to restore the original `select` element and delete the plugin element.
- `getContainer()` to get the container element.


## Issues and Contributions

You can report any issue you may encounter on the [GitHub Issue Tracker](https://github.com/florianraabe/bootstrap5-duallistbox/issues).

To contribute, please follow the [contribution guidelines](https://github.com/florianraabe/bootstrap5-duallistbox/blob/master/CONTRIBUTING.md).

## History

Check [Release](https://github.com/florianraabe/bootstrap5-duallistbox/releases) list.

## License

```
  Copyright 2024 Florian Raabe

  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
```

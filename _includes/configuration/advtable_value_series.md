## `advtable_value_series`

{{ site.requires_5_9v }}

The `advtable_value_series` option configures one or more series of values for populating cells in a table. This option can be used to create row identifiers.

**Type:** `Object`

**Default Value:**

```js
{
  // Natural number series
  numeric: { 
    title: 'Numeric',
    update: true,
    resizable: false,
    generator: `GeneratorFunction` // For details, see: 'Creating a value series generator'
  },
  // English alphabetic series
  alpha: {
    title: 'Alpha',
    update: true,
    resizable: false,
    generator: `GeneratorFunction` // For details, see: 'Creating a value series generator'
  },
}
```

Both default series are configured to update on table changes and not resize when using the resize bars.

Each top-level properties of the `advtable_value_series` object are used as the name of the value series and its configuration. In the following example, there are two value series named "`numbers`" and "`letters`":

```js
{
  numbers: { 
    title: 'Numbered',
    generator: `GeneratorFunction`
  },
  letters: {
    title: 'Lettered',
    generator: `GeneratorFunction`
  },
}
```

### Series configuration

| Name | Value | Requirement | Description |
| ---- | ----- | ----------- | ----------- |
| title | `string` | Required | The text shown in the UI for the series. |
| update | `boolean` | Optional | default: `false` - When `true`, the series values will be updated when changes are made to the table. |
| resizable | `boolean` | Optional | default: `true` - When `true`, table cells containing the series values can be resized using a mouse or touch device. |
| generator | `(info: GeneratorInfo, rowIndex: number, columnIndex: number) => GeneratorResult` | Required | For details on creating a value series generator, see: [Creating a value series generator](#creatingavalueseriesgenerator).  |

#### Creating a value series generator

The `generator` is a callback function used to specify how a table cell of a value series will update. The callback is passed information relating to: the generator and table cell, the row index, and column index of the table cell. For details, see: [GeneratorInfo](#generatorinfo). The callback should return an object containing the value and optionally, any classes and attributes to be applied to the table cell. For details, see: [GeneratorResult](#generatorresult).

If the "state" of the series needs to be kept between generator iterations, additional properties can be added to the generator result. The state can be accessed through the `prev` property of the `info` parameter. For details, see: [GeneratorInfo](#generatorinfo). 

##### GeneratorInfo

An object with the following properties is passed to the generator callback function as the `info` parameter.

| Name | Value | Description |
| ---- | ----- | ----------- |
| sectionType | `'thead'`, `'tbody'` or `'tfoot'` | The section of the table cell. |
| cellType | `'td'` or `'th'` | The type of the table cell. |
| getRowType | `() => 'header' | 'body' | 'footer'` | A function that returns the type of row the table cell is part of. A 'header' row is either a row that is part of a `thead` section or contains all `th` cells. |
| classes | `string[]` | The classes present on the table cell. |
| direction | `'row'` or `'column'` | The direction of the generator. |
| prev | `GeneratorResult` | The generator result from the previous iteration. |

##### GeneratorResult

The generator callback function should return an object with the following properties.

| Name | Value | Requirement | Description |
| ---- | ----- | ----------- | ----------- |
| classes | `string[]` | Optional | The classes to be applied to the table cell. |
| attributes | `Object` | Optional | The attributes to be applied to the table cell. The `attributes` should be provided as an object where each key is an attribute and each value is of type `string`, `boolean`, `number`, or `null`. A value of `null` for an attribute will remove the attribute from the table cell. |
| value | `string`, `number` or `undefined` | Optional | The value of the table cell. If the value is `undefined`, the editor will use the previous value of the table cell. |

### Example: Using `advtable_value_series`

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your html
  plugins: 'table advtable',
  menubar: 'table',
  toolbar: 'advtablerownumbering',
  advtable_value_series: {
    numeric: {
      title: 'Numeric',
      update: true,
      resizable: false,
      generator: function (info, rowIndex, columnIndex) {
        return {
          value: rowIndex + 1
        };
      }
    },
  }
});
```

---
group: graphql
title: CustomizableOptionInterface
redirect_from:
  - /guides/v2.4/graphql/product/customizable-option-interface.html
---

Customizable options for a product provide a way to offer customers a selection of options with a variety of text, selection, and date input types. All product types can contain customizable options.

`CustomizableOptionInterface` is defined in the `CatalogGraphQl` module, and its attributes can be used in any `products` query. This interface returns basic information about a customizable option and can be implemented by several types of configurable options:

*  Text area
*  Checkbox
*  Date picker
*  Drop-down menu
*  Text field
*  File picker
*  Multiple select box
*  Radio buttons

 {:.bs-callout-info}
Magento has not implemented all possible customizable product options for GraphQL.

`CustomizableOptionInterface` can contain the following attributes:

Attribute | Type | Description
--- | --- | ---
`option_id` | Int |  Deprecated. Use `uid` instead. The ID assigned to the option
`required` | Boolean | Indicates whether the option is required
`sort_order` | Int | The order in which the option is displayed
`title` |  String | The display name for this option
`uid` | ID! | The unique identifier for the `CustomizableOptionInterface` object

## CustomizableAreaOption object

`CustomizableAreaOption` contains information about a text area that is defined as part of a customizable option.

Attribute | Type | Description
--- | --- | ---
`product_sku` | String | The Stock Keeping Unit of the base product
`value` | `CustomizableAreaValue` | An object that defines a text area

### CustomizableAreaValue object

`CustomizableAreaValue` defines the attributes of a product whose page contains a customized text area.

Attribute | Type | Description
--- | --- | ---
`max_characters` | Int | The maximum number of characters that can be entered for this customizable option
`price_type` | PriceTypeEnum | FIXED, PERCENT, or DYNAMIC
`price` | Float | The price assigned to this option
`sku` | String | The Stock Keeping Unit for this option
`uid` | ID! | The unique ID for a `CustomizableAreaValue` object

## CustomizableCheckboxOption object

`CustomizableCheckboxOption` contains information about a set of checkbox values that are defined as part of a customizable option.

Attribute | Type | Description
--- | --- | ---
`value` | `CustomizableCheckboxValue` | An array that defines a set of checkbox values

### CustomizableCheckboxValue object

`CustomizableCheckboxValue` defines the attributes of a product whose page contains a customized set of checkbox values.

Attribute | Type | Description
--- | --- | ---
`option_type_id` | Int | The ID assigned to the value
`price_type` | PriceTypeEnum | FIXED, PERCENT, or DYNAMIC
`price` | Float | The price assigned to this option
`sku` | String | The Stock Keeping Unit for this option
`sort_order` | Int | The order in which the option is displayed
`title` | String | The display name for this option
`uid` | ID! | A string that encodes option details

## CustomizableDateOption object

`CustomizableDateOption` contains information about a date picker that is defined as part of a customizable option.

Attribute | Type | Description
--- | --- | ---
`product_sku` | String | The Stock Keeping Unit of the base product
`value` | `CustomizableDateValue` | An object that defines a date field in a customizable option.

### CustomizableDateValue object

`CustomizableDateValue` defines the attributes of a product whose page contains a customized date picker.

Attribute | Type | Description
--- | --- | ---
`price` | Float | The price assigned to this option
`price_type` | PriceTypeEnum | FIXED, PERCENT, or DYNAMIC
`sku` | String | The Stock Keeping Unit for this option
`type` | CustomizableDateTypeEnum | `DATE`, `DATE_TIME`, or `TIME`
`uid` | ID! | The unique ID for a `CustomizableDateValue` object

## CustomizableDropDownOption object

`CustomizableDropDownOption` contains information about a drop down menu that is defined as part of a customizable option.

Attribute | Type | Description
--- | --- | ---
`value` | `CustomizableDropDownValue` | An array that defines the set of options for a drop down menu

### CustomizableDropDownValue object

`CustomizableDropDownValue` defines the attributes of a product whose page contains a customized drop down menu.

Attribute | Type | Description
--- | --- | ---
`option_type_id` | Int | The ID assigned to the value
`price_type` | PriceTypeEnum | FIXED, PERCENT, or DYNAMIC
`price` | Float | The price assigned to this option
`sku` | String | The Stock Keeping Unit for this option
`sort_order` | Int | The order in which the option is displayed
`title` | String | The display name for this option
`uid` | ID! | The unique ID for a `CustomizableDropDownValue` object

## CustomizableFieldOption object

`CustomizableFieldOption` contains information about a text field that is defined as part of a customizable option.

Attribute | Type | Description
--- | --- | ---
`product_sku` | String | The Stock Keeping Unit of the base product
`value` | `CustomizableFieldValue` | An object that defines a text field

### CustomizableFieldValue object

`CustomizableFieldValue` defines the attributes of a product whose page contains a customized text field.

Attribute | Type | Description
--- | --- | ---
`max_characters` | Int | The maximum number of characters that can be entered for this customizable option
`price_type` | PriceTypeEnum | FIXED, PERCENT, or DYNAMIC
`price` | Float | The price of the custom value
`sku` | String | The Stock Keeping Unit for this option
`uid` | ID! | The unique ID for a `CustomizableFieldValue` object

## CustomizableFileOption object

{:.bs-callout-info}
The `CustomizableFileOption` object is currently not supported.

`CustomizableFileOption` contains information about a file picker that is defined as part of a customizable option.

Attribute | Type | Description
--- | --- | ---
`product_sku` | String | The Stock Keeping Unit of the base product
`value` | `CustomizableFileValue` | An object that defines a file name

### CustomizableFileValue object

{:.bs-callout-info}
The `CustomizableFileValue` object is currently not supported.

`CustomizableFileValue` defines the attributes of a product whose page contains a customized file picker.

Attribute | Type | Description
--- | --- | ---
`file_extension` | String | The file extension to accept
`image_size_x` | Int | The maximum width of an image
`image_size_y` | Int | The maximum height of an image
`price_type` | PriceTypeEnum | FIXED, PERCENT, or DYNAMIC
`price` | Float | The price assigned to this option
`sku` | String | The Stock Keeping Unit for this option
`uid` | ID! | The unique ID for a `CustomizableFileValue` object

## CustomizableMultipleOption object

`CustomizableMultipleOption` contains information about a multiselect that is defined as part of a customizable option.

Attribute | Type | Description
--- | --- | ---
`value` | `CustomizableMultipleValue` | An array that defines the set of options for a multiselect

### CustomizableMultipleValue object

`CustomizableMultipleValue` defines the price and sku of a product whose page contains a customized multiselect

Attribute | Type | Description
--- | --- | ---
`option_type_id` | Int | The ID assigned to the value
`price_type` | PriceTypeEnum | FIXED, PERCENT, or DYNAMIC
`price` | Float | The price assigned to this option
`sku` | String | The Stock Keeping Unit for this option
`sort_order` | Int | The order in which the option is displayed
`title` | String | The display name for this option
`uid` | ID! | The unique ID for a `CustomizableMultipleValue` object

## CustomizableRadioOption object

`CustomizableRadioOption` contains information about a set of radio buttons that are defined as part of a customizable option.

Attribute | Type | Description
--- | --- | ---
`value` | `CustomizableRadioValue` | An array that defines a set of radio buttons

### CustomizableRadioValue object

`CustomizableRadioValue` defines the attributes of a product whose page contains a customized set of radio buttons.

Attribute | Type | Description
--- | --- | ---
`option_type_id` | Int | The ID assigned to the value
`price_type` | PriceTypeEnum | FIXED, PERCENT, or DYNAMIC
`price` | Float | The price assigned to this option
`sku` | String | The Stock Keeping Unit for this option
`sort_order` | Int | The order in which the option is displayed
`title` | String | The display name for this option
`uid` | ID! | The unique ID for a `CustomizableRadioValue` object

`CustomizableRadioOption` contains information about a set of radio buttons that are defined as part of a customizable option.

Attribute | Type | Description
--- | --- | ---
`value` | `CustomizableRadioValue` | An array that defines a set of radio buttons

## Example usage

The following query returns information about the customizable options configured for the product with a `sku` of `xyz`.

**Request:**

```graphql
{
  products(filter: {sku: {eq: "xyz"}}) {
    items {
      uid
      name
      sku
      __typename
      ... on CustomizableProductInterface {
        options {
          title
          required
          sort_order
          uid
        }
      }
    }
  }
}
```

**Response:**

```json
{
  "data": {
    "products": {
      "items": [
        {
          "uid": "Mw==",
          "name": "T-shirt",
          "sku": "xyz",
          "__typename": "SimpleProduct",
          "options": [
            {
              "title": "Image",
              "required": false,
              "sort_order": 1,
              "uid": "Mx=="
            }
          ]
        }
      ]
    }
  }
}
```

The following query returns information about the customizable options configured for the product with a `sku` of `xyz` with Custom Option type Text Field.

*  Custom option Option Type is text field with required field.
*  Option Title is `Favorite Color`.
*  Price is `$5`, Price Type is `Fixed`, Option SKU is `favoriteColorSku` and Max. Characters is `20`.

**Request:**

```graphql
{
  products(filter: { sku: { eq: "xyz" } }) {
    items {
      id
      name
      sku
      __typename
      ... on CustomizableProductInterface {
        options {
          title
          required
          sort_order
          option_id
          ... on CustomizableFieldOption {
            value {
              uid
              sku
              price
              price_type
              max_characters
            }
          }
        }
      }
    }
  }
}
```

**Response:**

```json
{
  "data": {
    "products": {
      "items": [
        {
          "id": 10,
          "name": "Savvy Shoulder Tote",
          "sku": "24-WB05",
          "__typename": "SimpleProduct",
          "options": [
            {
              "title": "Favorite Color",
              "required": true,
              "sort_order": 2,
              "option_id": 2,
              "value": {
                "uid": "Y3VzdG9tLW9wdGlvbi8y",
                "sku": "favoriteColorSku",
                "price": 5,
                "price_type": "FIXED",
                "max_characters": 20
              }
            }
          ]
        }
      ]
    }
  }
}
```

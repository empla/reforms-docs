# Forms

If you need join your field in form, use `<reforms-form>`:

```vue
<reforms-form v-model="formValues">
  <reforms-input type="string" name="myvalue" />
  <reforms-input type="string" name="myvalue2" />
</reforms-form>
```

### Important note

In form attribute `name` in `reforms-input` is required.

## Use v-if

You can use `v-if` for `reforms-input`:

```vue
<reforms-form v-model="formValues">
  <reforms-input type="string" name="myinput"></reforms-input>
  <reforms-input type="string" name="myinput2" v-if="formValues.myinput == 'test'"></reforms-input>
</reforms-form>
```

## Events

Form emits events:

- submit
- beforeValidate
- validated
- validateFailed
- validateSuccess

## Schema

Forms can be created from schema:

```js
const myschema = {
    myfield: {
        type: 'string',
        attrs: {
            multiple: true,
        }
    },
    mygroup: {
        type: 'group',
        attrs: {
            // ...
        },
        children: {
            myfield: {
                type: 'string',
                attrs: {
                    label: 'My input'
                }
            },
        },
    },
};
```

Use schema in vue:

```vue
<reforms-form :schema="myschema">
  <button type="submit">Submit</button>
</reforms-form>
```

### v-if in schema

```js
const myschema = {
    myfield1: {
        type: 'string',
    },
    myfield2: {
        type: 'html',
        showIf(values) {
            return values.myfield1 === 'test';
        },
    },
};
```

## Validation

Forms can be validated:

```vue
<reforms-form>
  <reforms-input type="string" name="myfield" validation="required|string" />
</reforms-form>
```

> `submit` event will not be called, if validation fails.

### Validation in schema

validation can be used in schema, just need pass `validation` attribute:

```js
const myschema = {
    myfield1: {
        type: 'string',
        attrs: {
            validation: 'required|email',
        },
    },
};
```

### Disable validation

If you need disable validation add `:need-validation="false"` attribute:

```vue
<reforms-form :need-validation="false">
  ...
</reforms-form>
```

### Server side

Validation result from server:

```js
const validationResult: {
    fieldname: [
        {
            isValid: false,
            messages: [
                'Invalid input'
            ],
        },
    ],
    field2: [
        //...
    ],
}
```

If you have multiple input, you can add item:

```js
const validationResult: {
    fieldname: [
        {
            isValid: false,
            messages: [
                'Invalid input'
            ],
        },
        {
            isValid: false,
            messages: [
                'Invalid input2'
            ],
        },
    ],
}
```

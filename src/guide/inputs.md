# Inputs

If you need create an input, use `<reforms-input>` tag like this:

```vue
<reforms-input type="string" label="My Input" v-model="value" />
```

Where:

- `type` is input type **(required)**
- `label` is input label _(optional)_
- `v-model` is input value. Is _reactive_.

## Multiple

If you need multiple value (array like), you can use `multiple` attribute:

```vue
<reforms-input type="string" label="Multiple input" multiple />
```

Then reforms create "remove button" and "add button" for create and remove value.

## Sortable

Reforms supports sorting value with sort buttons. It's work if multiple is enabled

```vue
<reforms-input type="string" label="Multiple and sortable input" multiple sortable />
```

## Input group

You can group inputs, and groups can be multiple and sortable

```vue
<reforms-input type="group" name="mygroup" label="My Group">
  <reforms-input type="string" label="Value 1" name="value1" />
  <reforms-input type="string" label="Value 2" name="value2" />
</reforms-input>
```

### Important note

For inputs in group `name` attribute is **necessary**

## Input types

todo

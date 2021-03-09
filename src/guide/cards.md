# Cards

Cards can be used for display data:

```js
const myschema = {
    fieldname: {
        type: 'string',
        attrs: {
            label: 'Name',
        },
    }
};

const myvalues = {
    fieldname: 'test123',
};
```

```vue
<reforms-card :schema="myschema" :values="myvalues" />
```

> Cards work only with schema. If you don't need this use `<reforms-output>`


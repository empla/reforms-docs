 # Outputs
 
If you need only display value for user, use `<reforms-output>` like that:

```vue
<reforms-output type="string" name="myvalue" :value="value" label="My label" />
```

## Multiple value in output

If value is _multiple_ (like array) then need use `multiple` attribute:

```vue
<reforms-output type="string" multiple name="myvalue" :value="value" label="My label" />
```

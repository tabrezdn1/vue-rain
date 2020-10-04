# vue-rain


## Purpose
This is a vue component made for fun which renders slots in rain animation. It could be reallt useful if you want to create a shower effect with emojis.

### Example
```
 <VueRain :rainSpeed="100" :rainFade="3000">
    <!-- Rendering water drop emoji using slots-->
    <div><p>&#128167;</p></div>
  </VueRain>
```

### Props
There are currently the following props:

| Prop | Description | Required | Default |
| ------ | ------ | ------ | ------ |
| rainSpeed | This prop determines the speed of which the slots gets render, the lesser the more slots gets created. Consider it like the lesser it is the more its going to rain. It is measured in milliseconds. | `false` | `30` |
| rainFade | This prop is used to specify the time after which the rendered slot should fade away. It is measured in milliseconds. | `false` | `5000` |

### Slots
There are currently the following slots:

| Slot | Description | Example |
| ------ | ------ | ------ |
| `default` | This is default slot which will be rendered inside the component and the rain animation is added to this HTML. | It is in the above usage Example |

## Documentation
Coming soon...

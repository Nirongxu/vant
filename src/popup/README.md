# Popup

### Install

``` javascript
import { Popup } from 'vant';

Vue.use(Popup);
```

## Usage

### Basic Usage

```html
<van-button type="primary" @click="showPopup">
  Show Popup
</van-button>

<van-popup v-model="show">Content</van-popup>
```

```javascript
export default {
  data() {
    return {
      show: false
    }
  },

  methods: {
    showPopup() {
      this.show = true;
    }
  }
};
```

### Position

Use `position` prop to set popup display position

```html
<van-popup
  v-model="show"
  position="top"
  :style="{ height: '20%' }"
/>
```

### Round Corner

```html
<van-popup
  v-model="show"
  round
  position="bottom"
  :style="{ height: '20%' }"
/>
```

### Get Container

Use `get-container` prop to specify mount location

```html
<!-- mount to body -->
<van-popup
  v-model="show"
  get-container="body"
/>

<!-- mount to #app -->
<van-popup
  v-model="show"
  get-container="#app"
/>

<!-- Specify the mount location by function -->
<van-popup
  v-model="show"
  :get-container="getContainer"
/>
```

```js
export default {
  methods: {
    getContainer() {
      return document.querySelector('.my-container');
    }
  }
}
```

## API

### Props

| Attribute | Description | Type | Default |
|------|------|------|------|
| v-model | Whether to show popup | `Boolean` | `false` |
| overlay | Whether to show overlay | `Boolean` | `true` |
| position | Can be set to `top` `bottom` `right` `left` | `String` | `center` |
| overlay-class | Custom overlay class | `String` | - |
| overlay-style | Custom overlay style | `Object` | - |
| duration | Transition duration, unit second | `Number` | `0.3` |
| round | Whether to show round corner | `Boolean` | `false` | 
| lock-scroll | Whether to lock background scroll | `Boolean` | `true` |
| lazy-render | Whether to lazy render util appeared | `Boolean` | `true` |
| close-on-click-overlay | Whether to close when click overlay | `Boolean` | `true` |
| transition | Transition | `String` | `popup-slide` |
| get-container | Return the mount node for Popup | `String | () => HTMLElement` | - |

### Events

| Event | Description | Arguments |
|------|------|------|
| click | Triggered when click Popup | event: Event |
| open | Triggered when open Popup | - |
| opened | Triggered when opened Popup | - |
| close | Triggered when close Popup | - |
| closed | Triggered when closed Popup | - |
| click-overlay | Triggered when click overlay | - |

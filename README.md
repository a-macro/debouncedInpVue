# custom Vue3 Components

Includes:

-   `<DebouncedInput />` - input with built-in debouncing

## Build

```bash
npm install git+https://github.com/a-macro/debouncedInpVue.git
npm run build
```

## Use in project

```js
import { DebouncedInput } from 'custom-components';
```

```vue
<DebouncedInput v-model="search" :debounce="500" />
```

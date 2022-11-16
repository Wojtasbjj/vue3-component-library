# VUE3 TOASTRS LIBRARY

## Instalation

```sh
npm i @wgajda/vue3-component-library
```

## Usage

main.js

```sh
import { createApp } from "vue";
import App from "./App.vue";

import plugin from "@wgajda/vue3-component-library";

createApp(App).use(plugin).mount("#app");
```

You could now reference components in any Vue template of your project without importing anything.

```sh
<template>
    <Toastr />
</template>
```

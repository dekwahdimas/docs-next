# Perkenalan

::: info
Baru dalam Vue.js? Kunjungi [Panduan Esensial](/guide/introduction.html) kami untuk memulai.
:::

Panduan ini ditujukan untuk pengguna yang telah memiliki pengalaman Vue 2 sebelumnya. Kepada orang yang belajar tentang fitur baru dan perubahan di Vue 3. **Berikut ini bukan sesuatu yang harus Anda baca dari atas hingga bawah sebelum mencoba Vue 3.** Sementara terlihat banyak sekali perubahan, apa yang Anda ketahui dan cinta terhadap Vue tetaplah sama; tetapi kami ingin mengungkapkan secara seksama dan memberikan penjelasan secara mendetail dan contoh-contoh untuk setiap perubahan dokumen.

- [Quickstart](#quickstart)
- [Build Migrasi](#migration-build)
- [Fitur baru yang penting](#notable-new-features)
- [Perubahan terkini](#breaking-changes)
- [Pustaka yang mendukung](#supporting-libraries)

## Gambaran Umum

<br>
<iframe src="https://player.vimeo.com/video/440868720" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>

Mulai belajar Vue 3 di [Vue Mastery](https://www.vuemastery.com/courses-path/vue3).

## Quickstart

Jika Anda ingin mencoba Vue 3 dengan cepat di sebuah proyek baru:

- Melalui CDN: `<script src="https://unpkg.com/vue@next"></script>`
- In-browser playground di [Codepen](https://codepen.io/yyx990803/pen/OJNoaZL)
- In-browser Sandbox di [CodeSandbox](https://v3.vue.new)
- Scaffold melalui [Vite](https://github.com/vitejs/vite):

  ```bash
  npm init vite hello-vue3 -- --template vue # OR yarn create vite hello-vue3 --template vue
  ```

- Scaffold melalui [vue-cli](https://cli.vuejs.org/):

  ```bash
  npm install -g @vue/cli # OR yarn global add @vue/cli
  vue create hello-vue3
  # select vue 3 preset
  ```

## Build Migrasi

Jika Anda sudah mempunyai proyek Vue 2 atau pustaka yang ingin Anda tingkatkan ke versi Vue 3, kami menyediakan sebuah build dari Vue 3 beserta Vue 2 APIs yang kompatibel. Kunjungi halaman [Migrasi Build](./migration-build.html) untuk detail lebih lanjut.

## Fitur Baru yang Penting

Beberapa fitur baru yang akan membuat Anda tertarik di Vue 3 termasuk:

- [Composition API](/guide/composition-api-introduction.html)
- [Teleport](/guide/teleport.html)
- [Fragments](/guide/migration/fragments.html)
- [Emits Component Option](/guide/component-custom-events.html)
- [`createRenderer` API from `@vue/runtime-core`](https://github.com/vuejs/vue-next/tree/master/packages/runtime-core) to create custom renderers
- [SFC Composition API Syntax Sugar (`<script setup>`)](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0040-script-setup.md) <Badge text="experimental" type="warning" />
- [SFC State-driven CSS Variables (`v-bind` in `<style>`)](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0043-sfc-style-variables.md) <Badge text="experimental" type="warning" />
- [SFC `<style scoped>` can now include global rules or rules that target only slotted content](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0023-scoped-styles-changes.md)
- [Suspense](/guide/migration/suspense.html) <Badge text="experimental" type="warning" />

## Perubahan Terkini

Berikut ini adalah daftar perubahan terkini dari 2.x:

### Global API

- [Global Vue API diubah agar menggunakan sebuah instansi aplikasi](/guide/migration/global-api.html)
- [Global dan APIs Internal telah direkontruksi ulang sebagai tree-shakable](/guide/migration/global-api-treeshaking.html)

### Pengarahan Templat

- [Penggunaan `v-model` dalam komponen telah dikerjakan ulang, menggantikan `v-bind.sync`](/guide/migration/v-model.html)
- [Penggunaan `key` dalam simpul `<template v-for>` dan bukan-`v-for` telah diubah](/guide/migration/key-attribute.html)
- [Pendahuluan `v-if` dan `v-for` ketika digunakan dalam elemen yang sama telah diubah](/guide/migration/v-if-v-for.html)
- [`v-bind="object"` sekarang order-sensitive](/guide/migration/v-bind.html)
- [`v-on:event.native` modifier telah dihapus](./v-on-native-modifier-removed.md)
- [`ref` dalam `v-for` tidak lagi terdaftar sebagai array dari refs](/guide/migration/array-refs.html)

### Komponen

- [Functional components hanya dapat dibuat menggunakan plain function](/guide/migration/functional-components.html)
- [Atribut `functional` dalam komponen single-file (SFC) `<template>` dan opsi `functional` komponen telah usang](/guide/migration/functional-components.html)
- [Komponen async sekarang memerlukan metode `defineAsyncComponent` agar dapat dibuat](/guide/migration/async-components.html)
- [Komponen events harus dideklarasikan dengan opsi `emits`](./emits-option.md)

### Render Function

- [Render function API diubah](/guide/migration/render-function-api.html)
- [Properti `$scopedSlots` dihapus dan semua slots terekpos melalui `$slots` sebagai functions](/guide/migration/slots-unification.html)
- [`$listeners` telah dihapus / digabung dengan `$attrs`](./listeners-removed)
- [`$attrs` sekarang termasuk atribut `class` dan `style`](./attrs-includes-class-style.md)

### Elemen Kustom

- [Mengecek elemen kustom sekarang dilakukan saat kompilasi templat](/guide/migration/custom-elements-interop.html)
- [Penggunaan spesial `is` prop dibatasi hanya dapat dipesan oleh `<component>` tag](/guide/migration/custom-elements-interop.html#customized-built-in-elements)

### Beberapa Perubahan Lain

- Opsi siklus hidup `destroyed` diubah nama menjadi `unmounted`
- Opsi siklus hidup `beforeDestroy` diubah nama menjadi `beforeUnmount`
- [Props `default` factory function tidak lagi mengakses ke konteks `this`](/guide/migration/props-default-this.html)
- [API pengarahan kustom diubah untuk sejajar dengan siklus hidup komponen dan `binding.expression` dihapus](/guide/migration/custom-directives.html)
- [Opsi `data` harus selalu  dideklarasikan sebagai function](/guide/migration/data-option.html)
- [Opsi `data` dari mixins sekarang digabung secara dangkal](/guide/migration/data-option.html#mixin-merge-behavior-change)
- [Strategi pemaksaan atribut diubah](/guide/migration/attribute-coercion.html)
- [Beberapa kelas transition berubah nama](/guide/migration/transition.html)
- [`<TransitionGroup>` sekarang renders elemen tanpa wrapper secara default](/guide/migration/transition-group.html)
- [Ketika melihat sebuah array, callback akan hanya terpicu ketika array digantikan. Jika Anda ingin memicu ketika mutasi, opsi `deep` harus dispesifikkan.](/guide/migration/watch.html)
- `<template>` tags tanpa pengarahan spesial (`v-if/else-if/else`, `v-for`, atau `v-slot`) sekarang diperlakukan sebagai elemen polos dan akan mengakibatkan pada sebuah elemen native `<template>` daripada me-render konten didalamnya.
- [Aplikasi yang terpasang tidak mengubah elemen yang dipasangkan](/guide/migration/mount-changes.html)
- [Siklus hidup event dengan awalan `hook:` berubah menjadi `vnode-`](/guide/migration/vnode-lifecycle-events.html)

### Removed APIs

- [`keyCode` support as `v-on` modifiers](/guide/migration/keycode-modifiers.html)
- [$on, $off and \$once instance methods](/guide/migration/events-api.html)
- [Filters](/guide/migration/filters.html)
- [Inline templates attributes](/guide/migration/inline-template-attribute.html)
- [`$children` instance property](/guide/migration/children.html)
- [`propsData` option](/guide/migration/props-data.html)
- `$destroy` instance method. Users should no longer manually manage the lifecycle of individual Vue components.
- Global functions `set` and `delete`, and the instance methods `$set` and `$delete`. They are no longer required with proxy-based change detection.

## Supporting Libraries

All of our official libraries and tools now support Vue 3, but some of them are still in beta or release candidate status. You'll find details for the individual libraries below. Most are currently distributed using the `next` dist tag on npm. We intend to switch to `latest` once all the official libraries have compatible, stable versions.

### Vue CLI

<a href="https://www.npmjs.com/package/@vue/cli" target="_blank" noopener noreferrer><img src="https://img.shields.io/npm/v/@vue/cli"></a>

As of v4.5.0, `vue-cli` now provides the built-in option to choose Vue 3 when creating a new project. You can upgrade `vue-cli` and run `vue create` to create a Vue 3 project today.

- [Documentation](https://cli.vuejs.org/)
- [GitHub](https://github.com/vuejs/vue-cli)

### Vue Router

<a href="https://www.npmjs.com/package/vue-router/v/next" target="_blank" noopener noreferrer><img src="https://img.shields.io/npm/v/vue-router/next.svg"></a>

Vue Router 4.0 provides Vue 3 support and has a number of breaking changes of its own. Check out its [migration guide](https://next.router.vuejs.org/guide/migration/) for full details.

- [Documentation](https://next.router.vuejs.org/)
- [GitHub](https://github.com/vuejs/vue-router-next)
- [RFCs](https://github.com/vuejs/rfcs/pulls?q=is%3Apr+is%3Amerged+label%3Arouter)

### Vuex

<a href="https://www.npmjs.com/package/vuex/v/next" target="_blank" noopener noreferrer><img src="https://img.shields.io/npm/v/vuex/next.svg"></a>

Vuex 4.0 provides Vue 3 support with largely the same API as 3.x. The only breaking change is [how the plugin is installed](https://next.vuex.vuejs.org/guide/migrating-to-4-0-from-3-x.html#breaking-changes).

- [Documentation](https://next.vuex.vuejs.org/)
- [GitHub](https://github.com/vuejs/vuex/tree/4.0)

### Devtools Extension

We are working on a new version of the Devtools with a new UI and refactored internals to support multiple Vue versions. The new version is currently in beta and only supports Vue 3 (for now). Vuex and Router integration is also work in progress.

- For Chrome: [Install from Chrome web store](https://chrome.google.com/webstore/detail/vuejs-devtools/ljjemllljcmogpfapbkkighbhhppjdbg?hl=en)

  - Note: the beta channel may conflict with the stable version of devtools so you may need to temporarily disable the stable version for the beta channel to work properly.

- For Firefox: [Download the signed extension](https://github.com/vuejs/vue-devtools/releases/tag/v6.0.0-beta.2) (`.xpi` file under Assets)

### IDE Support

It is recommended to use [VSCode](https://code.visualstudio.com/) with our official extension [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur), which provides comprehensive IDE support for Vue 3.

### Other Projects

| Project               | npm                           | Repo                 |
| --------------------- | ----------------------------- | -------------------- |
| @vue/babel-plugin-jsx | [![rc][jsx-badge]][jsx-npm]   | [[GitHub][jsx-code]] |
| eslint-plugin-vue     | [![ga][epv-badge]][epv-npm]   | [[GitHub][epv-code]] |
| @vue/test-utils       | [![beta][vtu-badge]][vtu-npm] | [[GitHub][vtu-code]] |
| vue-class-component   | [![beta][vcc-badge]][vcc-npm] | [[GitHub][vcc-code]] |
| vue-loader            | [![rc][vl-badge]][vl-npm]     | [[GitHub][vl-code]]  |
| rollup-plugin-vue     | [![beta][rpv-badge]][rpv-npm] | [[GitHub][rpv-code]] |

[jsx-badge]: https://img.shields.io/npm/v/@vue/babel-plugin-jsx.svg
[jsx-npm]: https://www.npmjs.com/package/@vue/babel-plugin-jsx
[jsx-code]: https://github.com/vuejs/jsx-next
[vd-badge]: https://img.shields.io/npm/v/@vue/devtools/beta.svg
[vd-npm]: https://www.npmjs.com/package/@vue/devtools/v/beta
[vd-code]: https://github.com/vuejs/vue-devtools/tree/next
[epv-badge]: https://img.shields.io/npm/v/eslint-plugin-vue.svg
[epv-npm]: https://www.npmjs.com/package/eslint-plugin-vue
[epv-code]: https://github.com/vuejs/eslint-plugin-vue
[vtu-badge]: https://img.shields.io/npm/v/@vue/test-utils/next.svg
[vtu-npm]: https://www.npmjs.com/package/@vue/test-utils/v/next
[vtu-code]: https://github.com/vuejs/vue-test-utils-next
[jsx-badge]: https://img.shields.io/npm/v/@ant-design-vue/babel-plugin-jsx.svg
[jsx-npm]: https://www.npmjs.com/package/@ant-design-vue/babel-plugin-jsx
[jsx-code]: https://github.com/vueComponent/jsx
[vcc-badge]: https://img.shields.io/npm/v/vue-class-component/next.svg
[vcc-npm]: https://www.npmjs.com/package/vue-class-component/v/next
[vcc-code]: https://github.com/vuejs/vue-class-component/tree/next
[vl-badge]: https://img.shields.io/npm/v/vue-loader/next.svg
[vl-npm]: https://www.npmjs.com/package/vue-loader/v/next
[vl-code]: https://github.com/vuejs/vue-loader/tree/next
[rpv-badge]: https://img.shields.io/npm/v/rollup-plugin-vue/next.svg
[rpv-npm]: https://www.npmjs.com/package/rollup-plugin-vue/v/next
[rpv-code]: https://github.com/vuejs/rollup-plugin-vue/tree/next

::: info
For additional information on Vue 3 compatibility with libraries and plugins, be sure to check out [this issue in awesome-vue](https://github.com/vuejs/awesome-vue/issues/3544).
:::

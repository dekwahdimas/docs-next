---
title: Penghapusan $listeners
badges:
  - breaking
---

# `$listeners` telah dihapus <MigrationBadges :badges="$frontmatter.badges" />

## Gambaran Umum

Objek `$listeners` telah dihapuskan pada Vue 3. Event listeners sekarang bagian dari `$attrs`:

```js
{
  text: 'this is an attribute',
  onClose: () => console.log('close Event triggered')
}
```

## 2.x Sintaksis

Pada Vue 2, Anda dapat mengakses atribut-atribut yang disuguhkan ke komponen-komponen Anda melalui `this.$attrs`, dan event listeners dengan `this.$listeners`.
Pengkombinasian dengan `inheritAttrs: false`, mereka membolehkan para pengembang untuk mengaplikasikan atribut-atribut dan listener-listener ini ke semua elemen lain daripada ke elemen root:

```html
<template>
  <label>
    <input type="text" v-bind="$attrs" v-on="$listeners" />
  </label>
</template>
<script>
  export default {
    inheritAttrs: false
  }
</script>
```

## 3.x Sintaksis

Pada Vue 3's virtual DOM, event listeners sekarang hanyalah sebuah atribut, diawali dengan `on`, dan merupakan bagian dari objek `$attrs`, sehingga `$listeners` telah dihapuskan.

```vue
<template>
  <label>
    <input type="text" v-bind="$attrs" />
  </label>
</template>
<script>
export default {
  inheritAttrs: false
}
</script>
```

jika komponen ini mendapatkan sebuah atribut `id` dan sebuah listener `v-on:close`, objek `$attrs` sekarang akan tampak seperti ini:

```js
{
  id: 'my-input',
  onClose: () => console.log('close Event triggered')
}
```

## Strategi Migrasi

Hapus semua penggunaan dari `$listeners`.

[Flag build Migrasi: `INSTANCE_LISTENERS`](migration-build.html#compat-configuration)

## Baca juga

- [Relevant RFC](https://github.com/vuejs/rfcs/blob/master/active-rfcs/0031-attr-fallthrough.md)
- [Panduan Migrasi - `$attrs` memuat `class` & `style` ](./attrs-includes-class-style.md)
- [Panduan Migrasi - Perubahan pada Render Functions API](./render-function-api.md)
- [Panduan Migrasi - Opsi baru Emits](./emits-option.md)
- [Panduan Migrasi - Pengubah `.native` dihapuskan](./v-on-native-modifier-removed.md)

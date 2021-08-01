---
badges:
  - removed
---

# $children <MigrationBadges :badges="$frontmatter.badges" />

## Gambaran Umum

Properti `$children` telah dihapus dari Vue versi 3.0 dan tidak didukung lagi.

## Sintaks Vue versi 2.x

Pada Vue versi 2.x, pengembang dapat mengakses komponen turunan langsung dari sebuah objek menggunakan `this.$children`:

```vue
<template>
  <div>
    <img alt="Logo Vue" src="./assets/logo.png">
    <tombol-ku>Ubah logo</tombol-ku>
  </div>
</template>

<script>
import TombolKu from './MyButton'

export default {
  components: {
    TombolKu
  },
  mounted() {
    console.log(this.$children) // [VueComponent]
  }
}
</script>
```

## Perubahan pada Vue versi 3.x

In 3.x, the `$children` property is removed and no longer supported. Instead, if you need to access a child component instance, we recommend using [$refs](/guide/component-template-refs.html#template-refs).

## Migration Strategy

[Migration build flag: `INSTANCE_CHILDREN`](migration-build.html#compat-configuration)

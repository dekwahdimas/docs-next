---
title: Akses Props Fungsi Bawaan this
badges:
  - breaking
---

# Akses Props Fungsi Bawaan `this` <MigrationBadges :badges="$frontmatter.badges" />

Nilai bawaan props fungsi-fungsi factory tidak lagi memilki akses terhadap `this`.

Melainkan:

- Raw props didapatkan dari komponen yang dilewatkan menuju fungsi bawaan sebagai argumen;

- [inject](../composition-api-provide-inject.md) API dapat digunakan di dalam fungsi-fungsi bawaan.

```js
import { inject } from 'vue'

export default {
  props: {
    theme: {
      default (props) {
        // `props` merupakan nilai raw dilewatkan menuju komponen,
        // sebelum dilakukan type / default coercions
        // dapat juga menggunaan `inject` untuk mengakses properti yang diinjeksikan
        return inject('theme', 'default-theme')
      }
    }
  }
}
```

## Stategi Migrasi

[Flag build migrasi: `PROPS_DEFAULT_THIS`](migration-build.html#compat-configuration)

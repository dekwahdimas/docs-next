---
badges:
  - breaking
---

# Pengubah KeyCode <MigrationBadges :badges="$frontmatter.badges" />

## Gambaran Umum

Berikut adalah ringkasan singkat tentang apa yang telah berubah:

- **MERUSAK**: Pengunaan angka-angka, contoh. keyCodes, sebagai pengubah `v-on` tidak lagi didukung
- **MERUSAK**: `config.keyCodes` tidak lagi didukung

## 2.x Sintaksis

Pada Vue 2, `keyCodes` didukung sebagai satu cara untuk mengubah suatu metode `v-on`.

```html
<!-- versi keyCode -->
<input v-on:keyup.13="submit" />

<!-- versi alias -->
<input v-on:keyup.enter="submit" />
```

Tambahan, Anda dapat mendefinisikan alias Anda sendiri melalui opsi global `config.keyCodes`.

```js
Vue.config.keyCodes = {
  f1: 112
}
```

```html
<!-- versi keyCode -->
<input v-on:keyup.112="showHelpText" />

<!-- versi alias kustom -->
<input v-on:keyup.f1="showHelpText" />
```

## 3.x Sintaksis

Dikarenakan [`KeyboardEvent.keyCode` telah usang](https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode), sangat tidak masuk akal jika Vue 3 tetap mendukung hal ini. Sebagai gantinya, direkomendasikan untuk penggunaan nama kebab-case untuk semua key yang Anda akan gunakan sebagai pengubah.

```html
<!-- Pengubah Vue 3 Key pada v-on -->
<input v-on:keyup.page-down="nextPage">

<!-- kedua q dan Q cocok -->
<input v-on:keypress.q="quit">
```

Hasilnya, hal ini berarti bahwa `config.keyCodes` juga telah usang dan tidak lagi didukung.

## Strategi dalam Migrasi

Untuk semua yang memakai `keyCode` pada codebase kalian, kami merekomendasikan pengubahaan `keyCode` menjadi penamaan kebab-cased yang setara.

keys sebagai tanda baca dapat dituliskan secara literal. contoh. untuk key `,`:

```html
<input v-on:keypress.,="commaPress">
```

Limitasi dari sintaksis mencegah beberapa karakter untuk dicocokan, seperti `"`, `'`, `/`, `=`, `>`, dan `.`. Sebagai gantinya, untuk karakter-karakter tersebut Anda dapat cek `event.key` di dalam listener.

[Flag build migrasi:](migration-build.html#compat-configuration)

- `CONFIG_KEY_CODES`
- `V_ON_KEYCODE_MODIFIER`

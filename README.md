# Translasi dokumentasi Vue 3
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-6-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

_Repository_ berikut berisi terjemahan dokumentasi Vue 3 (vue-next) ke dalam Bahasa Indonesia. Anda dapat ikut berkontribusi dengan cara memperhatikan [Roadmap](https://github.com/vuejs-id/docs-next/projects/1) dan [Tata Cara Berkontribusi](https://github.com/vuejs-id/docs-next#tata-cara-berkontibusi).

Adapun situs dokumentasi Vue 3 dapat diakses pada tautan di bawah ini:
- [Bahasa Inggris](https://v3.vuejs.org/)
- [Bahasa Indonesia](https://v3-vuejsid-docs.netlify.app/)

## Tata Cara Berkontribusi

Perhatikan Tata Cara Berkontribusi kami dijabarkan ke .....

## Pengembangan Situs

1. _Clone repository_

```bash
git clone https://github.com/vuejs-id/docs-next.git
```

2. Instalasi _dependencies_

```bash
yarn # atau npm install
# proyek memakai yarn 1.x
```

3. Menjalankan situs pada komputer Anda

```bash
yarn serve # or npm run serve
```

Situs kemudian dapat diakses pada browser Anda melalui [http://localhost:8080/](http://localhost:8080/).

Proyek ini memerlukan versi Node.js 12+.

## *Deployment*

Melalui Netlify, situs akan diperbarui secara otomatis ketika _commit_ baru di-_push_ ke _branch_ `indonesian`. Akun Netlify dipegang dan dikelola oleh [@mandaputtra](https://github.com/mandaputtra).

## FAQ

### Glosarium

Glosarium dibuat untuk memudahkan kontributor dalam menerjemahkan kata-kata yang sering muncul pada dokumentasi resmi Vue.js. Glosarium dapat dilihat pada tautan berikut.
- [Glosarium Vuejs-id](https://github.com/vuejs-id/docs/blob/master/GLOSARIUM.md)
- [Glosarium Frontend Indonesia](https://github.com/frontend-id/glosarium)

### Bagaimana Menyinkronkan _Repository_ Vuejs-id dengan _Repository Upstream_ Vuejs

Vuejs-id menggunakan bot _[wei/pull]_(https://github.com/wei/pull) dengan konfigurasi yang dapat dibaca di [sini](https://github.com/vuejs-id/docs-next/blob/indonesian/.github/pull.yml). 

Bot _wei/pull_ memungkinkan Vuejs-id untuk menyimpan dan menyinkronkan _repository upstream_ pada _branch master_. _Branch_ ini dapat menjadi referensi jika bot _wei/pull_ mengalami _merge conflict_ pada saat melakukan _merge_ PR ke _branch indonesian_.

Vuejs-id menerima saran dan masukan apabila terdapat solusi yang lebih baik mengenai sistem sinkronisasi kami.

### Apakah contoh kode perlu diterjemahkan?

Tidak, karena:

- Terdapat beberapa contoh kode yang memiliki demo interaktif menggunakan CodePen. Jika contoh kode diterjemahkan, maka pembaca membutuhkan lebih banyak waktu untuk memahami contoh kode pada dokumentasi dengan contoh kode pada CodePen. Terkecuali jika kontributor dan Vuejs-id dapat menyediakan CodePen tersendiri untuk masing-masing demo interaktif.
- Beberapa hasil terjemahan dokumentasi Vue.js selain Bahasa Indonesia tidak menerjemahkan contoh kode, khususnya pada bagian penamaan variabel.
- Pengecualian untuk komentar pada contoh kode karena dapat menjelaskan bagian-bagian tertentu.

## Para Kontributor ✨

Terima kasih untuk kontribusi yang telah diberikan oleh para kontributor berikut ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="http://mandaputtra.github.io"><img src="https://avatars1.githubusercontent.com/u/23342943?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Manda Putra</b></sub></a><br /><a href="https://github.com/vuejs-id/docs-next/commits?author=mandaputtra" title="Code">💻</a> <a href="https://github.com/vuejs-id/docs-next/commits?author=mandaputtra" title="Documentation">📖</a></td>
    <td align="center"><a href="https://jefrydco.id"><img src="https://avatars0.githubusercontent.com/u/20434351?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Jefry Dewangga</b></sub></a><br /><a href="https://github.com/vuejs-id/docs-next/commits?author=jefrydco" title="Documentation">📖</a></td>
    <td align="center"><a href="http://namchee.netlify.app"><img src="https://avatars1.githubusercontent.com/u/32661241?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Cristopher</b></sub></a><br /><a href="#translation-Namchee" title="Translation">🌍</a></td>
    <td align="center"><a href="http://website-reza.vercel.app"><img src="https://avatars3.githubusercontent.com/u/9331014?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Reza Z. Ramadan</b></sub></a><br /><a href="#translation-RezaZR" title="Translation">🌍</a></td>
    <td align="center"><a href="http://zaiinhs.me"><img src="https://avatars.githubusercontent.com/u/53314006?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Zainal Abidin</b></sub></a><br /><a href="#translation-zaiinhs" title="Translation">🌍</a></td>
    <td align="center"><a href="http://mufidu.com"><img src="https://avatars.githubusercontent.com/u/70360519?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Muhammad Mufid Utomo</b></sub></a><br /><a href="#translation-mufidu" title="Translation">🌍</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!

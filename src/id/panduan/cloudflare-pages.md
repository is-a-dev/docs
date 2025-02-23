---
label: Cloudflare Pages
icon: ../../media/cloudflare.svg
tags:
    - guides
---

### Eits! Sebelumnya, Kamu harus fork repositori [is-a-dev/register](https://github.com/is-a-dev/register) dulu di GitHub. Abis itu baru mulai prosesnya

# Membuat Cloudfare Pages dengan subdomain is-a.dev

Ini adalah panduan tentang cara membuat website Cloudflare Pages dan mengarahkannya ke subdomain is-a.dev kamu

## Membuat website Cloudflare Pages

Pertama, kamu harus membuat website di Cloudflare Pages. Ikuti petunjuknya di [Cloudflare Pages Getting started guide](https://developers.cloudflare.com/pages/get-started/guide/) (bahasa Inggris)

### Mengarahkan subdomain kamu ke website Cloudflare Pages

Habis itu, kamu perlu mengarahkan subdomain is-a.dev kamu ke website Cloudflare Pages kamu. Kamu bisa ikuti petunjuknya di [Cloudflare Pages Custom Domains Guide](https://developers.cloudflare.com/pages/platform/custom-domains/#add-a-custom-domain) (bahasa Inggris). Ikutin yang "Add a custom domain" aja ya, habis itu balik ke website ini untuk melanjutkan ke tahap berikutnya

### Membuat file Domain

Masuk ke repositori yang sudah kamu fork sebelumnya

Di dalam folder `domains`, buat file JSON baru untuk subdomain kamu

(semisal, `akukeren.json`. Teks 'akukeren' akan menjadi subdomain kamu, yang bisa di terjemahkan ke `akukeren.is-a.dev`) 

dan buatlah pull request. File-nya harus memenuhi seperti ini ya! (Btw yang email bisa opsional ya. Bisa di hapus key sama value 'email' nya)

```json
{
    "owner": {
        "username": "<username GitHub kamu>",
        "email": "<email kamu>"
    },
    "record": {
        "CNAME": "website-kamu.pages.dev"
    }
}
```

**Note:** Di bagian 'owner', kamu bisa menambahkan username social media kamu, seperti Discord. Jika kamu ingin menambahkan akun social media lagi, kamu bisa menghapus bagian 'email' di dalam file JSON tersebut. Tapi, kamu tetap diwajibkan untuk mencantumkan username Github kamu.

Jangan lupa kasih cuplikan (bisa sekilas) tentang/isi website ini, di pull requestnya yak.

### Website kamu sudah live!

Kalau kamu sudah mengikuti semua tahapannya secara benar, website kamu bisa live setelah pull request kamu sudah tergabung

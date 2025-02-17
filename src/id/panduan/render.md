---
icon: ../../media/render.svg
label: Render
tags:
    - guides
---

### Eits! Sebelumnya, Kamu harus fork repositori [is-a-dev/register](https://github.com/is-a-dev/register) dulu di GitHub. Abis itu baru mulai prosesnya

## Membuat Render dengan subdomain is-a.dev

Ini adalah panduan tentang cara membuat Render service dan mengarahkannya ke subdomain is-a.dev kamu

### Membuat Render Service

Pertama, (ya pasti) buat service dulu di Render. Ikuti petunjuknya di [Render Docs](https://docs.render.com/) (bahasa Inggris).

### Membuat file Domain

Masuk ke repositori yang sudah kamu fork sebelumnya

Buat file JSON di dalam directory `domains` dan tambahkan `<subdomain kamu>.json` (Jangan lupa ganti `<subdomain kamu>` ya dengan nama subdomain yang kamu inginkan). Habis itu buat pull request:

Note: "A" itu ditaruh dengan alamat IP-nya Render

```json
{
    "description": "Describe the use of this subdomain",
    "repo": "https://github.com/github-username/github-repository",
    "owner": {
        "username": "github-username",
        "email": "me@example.com"
    },
    "record": {
        "A": ["216.24.57.1"]
    }
}
```

**Note:** Di bagian 'owner', kamu bisa menambahkan username social media kamu, seperti Discord. Jika kamu ingin menambahkan akun social media lagi, kamu bisa menghapus bagian 'email' di dalam file JSON tersebut. Tapi, kamu tetap diwajibkan untuk mencantumkan username Github kamu.

Jangan lupa kasih cuplikan (bisa sekilas) tentang/isi website ini, di pull requestnya yak.

## Configuring Render

- Masuk ke **Settings > Custom Domains** dan tambahkan `<subdomain kamu>.is-a.dev` di kolom yang tersedia
- Sebenarnya sih Render bakal ngasih tahap verifikasi lagi, tapi kita skip aja soalnya kan sudah kita tambahin IP-nya (`216.24.57.1`).

### Tahap Terakhir

- Nunggu biar DNS ke propagate. Bisa sampai beberapa menit, atau lebih dari sejam
- Render Service kamu bisa diakses di `<subdomain kamu>.is-a.dev` deh!
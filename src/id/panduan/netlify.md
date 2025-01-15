---
icon: ../../media/netlify.svg
label: Netlify
tags:
    - guides
---

### Eits! Sebelumnya, Kamu harus fork repositori [is-a-dev/register](https://github.com/is-a-dev/register) dulu di GitHub. Abis itu baru mulai prosesnya

## Membuat website Netlify dengan subdomain is-a.dev

Ini adalah panduan tentang cara membuat website Netlify dan mengarahkannya ke subdomain is-a.dev kamu

### Membuat website Netlify

Pertama, (ya pasti) buatlah website dulu di Netlify. Ikuti petunjuknya di [Netlify Docs](https://docs.netlify.com/) (bahasa Inggris).

### Membuat file Domain
Masuk ke repositori yang sudah kamu fork sebelumnya

Buat file JSON di dalam directory `domains` dan tambahkan `<subdomain kamu>.json` (Jangan lupa ganti `<subdomain kamu>` ya dengan nama subdomain yang kamu inginkan). Habis itu buat pull request:

Note: "A" itu ditaruh dengan alamat IP-nya Netlify
```json
{
    "description": "Jelaskan kegunaan subdomain ini",
    "owner": {
        "username": "<username GitHub kamu>",
        "email": "<email kamu>"
    },
    "record": {
        "A": ["75.2.60.5"]
    }
}
```

**Note:** Di bagian 'owner', kamu bisa menambahkan username social media kamu, seperti Discord. Jika kamu ingin menambahkan akun social media lagi, kamu bisa menghapus bagian 'email' di dalam file JSON tersebut. Tapi, kamu tetap diwajibkan untuk mencantumkan username Github kamu.

Jangan lupa kasih cuplikan (bisa sekilas) tentang/isi website ini, di pull requestnya yak.

## Configuring Netlify

- Masuk ke dashboard Netlify di [sini](https://app.netlify.com)
- Pilih website kamu di dashboard tersebut
- Masuk ke **Site Settings > Domain Management > Custom Domains** dan tambahkan `<subdomain kamu>.is-a.dev` di kolom yang ada
- Sebenarnya sih Netlify bakal ngasih tahap verifikasi lagi, tapi kita skip aja soalnya kan sudah kita tambahin IP-nya (`75.2.60.5`).

### Tahap terakhir

- Nunggu biar DNS ke propagate. Bisa sampai beberapa menit, atau lebih dari sejam
- Website Netlify kamu bisa diakses di `<subdomain kamu>.is-a.dev` deh!
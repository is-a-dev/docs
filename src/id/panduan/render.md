---
icon: /media/render.svg
label: Render
tags:
    - guides
---

## Setting up Render with is-a.dev Subdomain

This guide will walk you through the process of setting up a Render deployment and pointing your is-a.dev subdomain to it.

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

**Note:** Di bagian 'owner', kamu bisa menambahkan username social media kamu, seperti Discord. Jika kamu ingin menambahkan akun social media lagi, kamu bisa menghapus bagian 'email' di dalam file JSON tersebut. Tapi, kamu tetap diwajibkan untuk mencantumkan username Github kamu. Jangan lupa kasih cuplikan (bisa sekilas) di dalam server DanBot Host yang kamu punya, ke pull request kamu ya

## Configuring Render

- After the pull request is merged, you may need to configure your Render service to use the new subdomain. Go to your Render service's dashboard.
- Navigate to **Settings > Custom Domains** and add `subdomain.is-a.dev` in the given field.
- Render will provide a verification step, usually requiring you to add a DNS record. This step should be skipped if your subdomain is already pointing to Render's IP address (`216.24.57.1`).

### Tahap Terakhir

- Nunggu biar DNS ke propagate. Bisa sampai beberapa menit, atau lebih dari sejam
- Website Render kamu bisa diakses di `<subdomain kamu>.is-a.dev` deh!
---
label: ImprovMX
icon: ../../media/improvmx.svg
tags:
    - guides
---

### Eits! Sebelumnya, Kamu harus fork repositori [is-a-dev/register](https://github.com/is-a-dev/register) dulu di GitHub. Abis itu baru mulai prosesnya

## Membuat ImprovMX dengan subdomain is-a.dev

Ini adalah panduan tentang cara menghubungkan ImprovMX dengan subdomain is-a.dev kamu

### Sebelum ini..

1. Sudah punya akun ImprovMX. Kalau belom ke [sini](https://improvmx.com) dan buat akunnya.
2. Sudah menambahkan subdomain is-a.dev mu di [ImprovMX dashboard](https://app.improvmx.com/)

### Membuat file Domain
Masuk ke repositori yang sudah kamu fork sebelumnya

Buat file JSON di dalam directory `domains` dan tambahkan `<subdomain kamu>.json` (Jangan lupa ganti `<subdomain kamu>` ya dengan nama subdomain yang kamu inginkan). 

Yang 'record' nya gausah di *modif*, udah aman kok. 
Tinggal bagian 'owner' aja

Habis itu buat pull request:
```json
{
    "owner": {
        "username": "<username GitHub kamu>",
        "email": "<email kamu>"
    },
    "record": {
        "MX": ["mx1.improvmx.com", "mx2.improvmx.com"],
        "TXT": ["v=spf1 include:spf.improvmx.com ~all"]
    }
}
```

### Configuring

Setelah selesai, ImprovMX kamu sudah siap dipakai *deh*, dengan subdomain kamu. Otomatis kok, gaperlu nunggu
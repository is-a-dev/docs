---
icon: ../../media/discord.svg
label: Discord koneksi Domain
tags:
    - guides
---

# Membuat koneksi domain untuk Discord, dengan subdomain is-a.dev

Ini adalah panduan tentang cara membuat koneksi subdomain is-a.dev kamu ke Discord

## Mendapatkan teks verifikasi

1. Buka aplikasi discord kamu dan tekan `Settings`.
   ![](../../media/discord/step_1.png)

2. Buka  `Connections`.
   ![](../../media/discord/step_2.png)

3. Tekan `View more`.
   ![](../../media/discord/step_3.png)

4. Tekan tombol domain (yang ada logo globe).
   ![](../../media/discord/step_4.png)

5. Ketik subomain is-a.dev kamu di dalam kolom tersebut  (misal, `example.is-a.dev`).
   ![](../../media/discord/step_5.png)

6. Ambil teks verifikasi tersebut (berada di kolom `Content`)
   ![](../../media/discord/step_6.png)

### Membuat file Domain

Buatlah sebuah file JSON baru di dalam directory `domains`, dengan nama `_discord.<nama subdomain kamu>.json` dengan format ini:

```json
{
    "owner": {
        "username": "github-username",
        "email": "email@address"
    },
    "record": {
        "TXT": "teks-verifikasi-discord"
    }
}
```

## Configuration

Setelah pull request kamu sudah tergabung, ulangi proses tersebut (tapi gausah ambil teks verifikasinya) sampai kamu pencet tombol `Verify`. Kalau ada error seperti `Unable to verify your domain`, coba tunggu beberapa menit (bisa sehari juga). Bisa jadi karena DNS nya belum ke-update
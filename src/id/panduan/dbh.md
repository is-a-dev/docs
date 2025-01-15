---
label: DanBot Hosting
tags: guides
icon: ../../media/dbh.png
---s

### Eits! Sebelumnya, Kamu harus fork repositori [is-a-dev/register](https://github.com/is-a-dev/register) dulu di GitHub. Abis itu baru mulai prosesnya

# Membuat server DanBot Hosting dengan subdomain is-a.dev

Ini adalah panduan tentang cara membuat server DanBot Hosting dan mengarahkannya ke subdomain is-a.dev kamu

## Mengambil Proxy IP

Jalankan command ini di [Discord server DanBot Hosting](https://discord.gg/dbh) di dalam channel #commands.

```
dbh!server proxy
```
Kamu akan mendapatkan pesan seperti ini:

![](../../media/dbh_proxy/1.jpg)

Jika kamu berada di free plan, kamu hanya bisa memilih proxy yang berada di US. Tetapi, jika kamu adalah Donator, kamu bisa pilih proxy khusus Donator, setelah itu catat alamat IP dari proxy yang kamu pilih.

### Membuat file Domain

Masuk ke repositori yang sudah kamu fork sebelumnya

Kamu perlu membuat file JSON di dalam `domains` (semisal, `domains/subdomain.json`) dengan format ini. Habis itu buatlah pull request:

```json
{
    "description": "Jelaskan kegunaan subdomain ini",
    "owner": {
        "username": "<username GitHub kamu>",
        "email": "<email kamu>"
    },
    "record": {
        "A": ["proxy-ip-disini"]
    }
}
```

**Note:** Di bagian 'owner', kamu bisa menambahkan username social media kamu, seperti Discord. Jika kamu ingin menambahkan akun social media lagi, kamu bisa menghapus bagian 'email' di dalam file JSON tersebut. Tapi, kamu tetap diwajibkan untuk mencantumkan username Github kamu.

Jangan lupa kasih cuplikan (bisa sekilas) di dalam server DanBot Host yang kamu punya, ke pull request kamu ya

## Configuring

Setelah pull requestnya sudah digabung, ambil server ID kamu  dengan menjalankan command di [Discord server DanBot Hosting](https://discord.gg/dbh) dan masuk ke dalam channel #commands.

```
dbh!server list
```

Kamu akan mendapatkan pesan seperti ini:

![](../../media/dbh_proxy/2.jpg)

Catat server ID yang berada pada pesan tersebut, terus jalankan command ini:

```
dbh!server proxy <subdomain kamu>.is-a.dev <server ID kamu>
```

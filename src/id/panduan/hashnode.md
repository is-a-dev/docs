---
icon: ../../media/hashnode.svg
label: Hashnode
tags:
    - guides
---

### Eits! Sebelumnya, Kamu harus fork repositori [is-a-dev/register](https://github.com/is-a-dev/register) dulu di GitHub. Abis itu baru mulai prosesnya

## Hashnode Blog

Ini adalah panduan tentang cara membuat website Hashnode Blog dan mengarahkannya ke subdomain is-a.dev kamu. Kalau nggak sih bisa pakai opsi default nya, `hashnode.dev`

---

### Menambahkan subdomain is-a.dev kamu ke Hashnode
1. Login ke akun Hashnode kamu

2. Tekan **avatar**/**profil**. Bawah kiri kalau di **desktop**, atau atas kanan kalau di **mobile**.
   ![Hashnode's Feed](https://cdn.hashnode.com/res/hashnode/image/upload/v1614932849541/cBNDGKXMj.png?auto=compress)

3. Tekan **Blog Dashboard** option dari popup yang muncul
   ![Hashnode's Feed](https://cdn.hashnode.com/res/hashnode/image/upload/v1614937218081/InvxVHXDy.png?auto=compress)

4. Masuk ke tab **Domain** ketik subdomain is-a.dev kamu (misal, `gwkeren.is-a.dev`) tanpa **www** atau **https://** prefix di dalam kolomnya. Habis itu klik **Update**.
   ![Hashnode's Blog Domain Tab](https://cdn.hashnode.com/res/hashnode/image/upload/v1614937377176/0cwddAywO.png?auto=compress)


### Membuat file Domain
Masuk ke repositori yang sudah kamu fork sebelumnya

Buat file JSON di dalam directory `domains` dan tambahkan `<subdomain kamu>.json` (Jangan lupa ganti `<subdomain kamu>` ya dengan nama subdomain yang kamu inginkan). Habis itu buat pull request:

```json
{
    "description": "Jelaskan kegunaan subdomain ini",
    "owner": {
        "username": "<username GitHub kamu>",
        "email": "<email kamu>"
    },
    "record": {
        "CNAME": ["hashnode.network"]
    }
}
```

## Configuration

Setelah selesai, blog Hashnode kamu sudah siap dipakai *deh*, dengan subdomain kamu.

Perubahan ini dapat memakan waktu mulai dari sejam hingga sekitar 2 hari, jadi nunggu yak. Kemungkinan besar siapnya dalam waktu sejam.

## Butuh pertanyaan?

Jika kamu ketemu isu/masalah, atau butuh bantuan untuk kedepannya, bisa ikuti materi ini ya:

- [Hashnode Domain Mapping Guide](https://support.hashnode.com/docs/mapping-domain/) (bahasa Inggris): Instruksi secara detail untuk menambahkan domain kamu di Hashnode.
- [Hashnode Support Center](https://support.hashnode.com/) (bahasa Inggris): Support center terkat dengan Hashnode, bisa lebih umum.

_*Harap dicatat bahwa is-a.dev tidak berafiliasi dengan Hashnode. Jika Anda mengalami masalah dengan blog Hashnode Anda, silakan mencari bantuan melalui channel Hashnode Support. Kami tidak dapat membantu terkait masalah khusus Hashnode._

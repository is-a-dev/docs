---
icon: ../../media/replit.svg
label: Replit
tags:
    - guides
---

### Eits! Sebelumnya, Kamu harus fork repositori [is-a-dev/register](https://github.com/is-a-dev/register) dulu di GitHub. Abis itu baru mulai prosesnya

## Membuat Replit dengan subdomain is-a.dev

### Membuat project/workspace baru
Ikuti instruksi di [Replit Workspace Guide](https://docs.replit.com/replit-workspace/introduction-to-workspace#how-to-create-a-repl) (bahasa Inggris) untuk cara membuat project.

### Menyambungkan project ke subdomain is-a.dev kamu

Sejak Replit Workspaces sudah berubah (semuanya), bisa ikuti instruksinya di dokumentasi baru [Replit Deployment Custom Domains Guide](https://docs.replit.com/cloud-services/deployments/custom-domains#connecting-your-domain-to-your-deployment) (bahasa Inggris). 

Note: Kamu butuh langganan Replit Deployment biar bisa dilakukan, atau baca selengkapnya di [Pricing - Replit](https://replit.com/pricing) (bahasa Inggris).

### Membuat file Domain

Setelah klik "Link a Domain" di menu Replit Deployment (yang ada pada panduan sebelumnya), kamu akan menemukan pesan ini

![image](https://docimg.replit.com/images/deployments/custom-domains/03.png)

(Di contoh screenshot itu, mereka memakai domain `hat-tip.cc`. Tapi kalau di situasi kita, harusnya `<subdomain kamu>.is-a.dev`)

1. Catat IP dari 'A' nya dan value TXT nya. 

2. Masuk ke repositori yang sudah kamu fork sebelumnya

3. Buat file JSON baru didalam directory `domains` dan namai seperti `<subdomain kamu>.json` dengan konten ini: (Btw, emailnya ga wajib yak kalau udah taruh 'username')

Kalau udah dibuat pull request
```json
{
    "owner": {
        "username": "<username GitHub kamu>",
        "email": "<email kamu>"
    },
    "record": {
        "A": ["<IP disini, ada setelah A Record>"],
        "TXT": "<TXT value disini, ada setelah TXT Record>"
    }
}
```

**Note:** Di bagian 'owner', kamu bisa menambahkan username social media kamu, seperti Discord. Jika kamu ingin menambahkan akun social media lagi, kamu bisa menghapus bagian 'email' di dalam file JSON tersebut. Tapi, kamu tetap diwajibkan untuk mencantumkan username Github kamu.

Jangan lupa kasih cuplikan (bisa sekilas) tentang/isi website ini, di pull requestnya yak.

## Finish

Setelah pull request kamu sudah tergabung, kamu bisa akses Replit mu dengan subdomain is-a.dev kamu *deh*
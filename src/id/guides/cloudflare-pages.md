---
label: Cloudflare Pages
icon: ../../media/cloudflare.svg
tags:
    - guides
---

# Membuat Cloudfare Pages dengan subdomain is-a.dev

Ini adalah panduan tentang cara membuat website Cloudflare Pages dan mengarahkannya ke subdomain is-a.dev kamu

## Membuat website Cloudflare Pages

Pertama, kamu harus membuat website di Cloudflare Pages. Ikuti petunjuknya di [Cloudflare Pages Getting started guide](https://developers.cloudflare.com/pages/get-started/guide/) (bahasa Inggris)

### Mengarahkan subdomain kamu ke website Cloudflare Pages

Habis itu, kamu perlu mengarahkan subdomain is-a.dev kamu ke website Cloudflare Pages kamu. Kamu bisa ikuti petunjuknya di [Cloudflare Pages Custom Domains Guide](https://developers.cloudflare.com/pages/platform/custom-domains/#add-a-custom-domain) (bahasa Inggris). Ikutin yang "Add a custom domain" aja ya, habis itu balik ke website ini untuk melanjutkan ke tahap berikutnya

### Membuat file Domain

Di dalam folder `domains`, buat file JSON baru untuk subdomain kamu (semisal, `domains/subdomain.json`) dan buatlah pull request. File-nya harus memenuhi seperti ini ya! (Btw yang email bisa opsional ya. Bisa di hapus key sama value 'email' nya)

```json
{
    "owner": {
        "username": "usename-github-kamu",
        "email": "email-kamu@example.com"
    },
    "record": {
        "CNAME": "website-kamu.pages.dev"
    }
}
```

### Website kamu sudah live!

Kalau kamu sudah mengikuti semua tahapannya secara benar, website kamu bisa live setelah pull request kamu sudah tergabung

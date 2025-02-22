---
label: Páginas de Cloudflare
icon: /media/cloudflare.svg
tags:
    - guides
    - spanish
---

# Configurando páginas de Cloudflare con un subdominio is-a.dev

Esta guía te guiará a través del proceso de configuración de una página de Cloudflare y el de asignarle tu subdominio is-a.dev a ella.

## Crear un sitio de Cloudflare

Primero, necesitarás crear un sitio en Cloudflare Pages. Sigue las instrucciones en la [Guía de Inicio de Cloudflare Pages](https://developers.cloudflare.com/pages/get-started/guide/).

### Asignarle tu subdominio a tu sitio de Cloudflare Pages

A continuación, necesitarás asignar tu subdominio is-a.dev a tu sitio de Cloudflare Pages. Sigue las instrucciones en la [Guía de Dominios Personalizados de Cloudflare Pages](https://developers.cloudflare.com/pages/platform/custom-domains/#add-a-custom-domain). Sólo nos importa la sección "Añadir un dominio personalizado", al terminar, vuelve a esta guía para los pasos siguientes.

### Crear el archivo de dominio

En el directorio `domains`, crea un nuevo archivo JSON para tu subdominio (`domains/subdominio.json`) y envía una pull request. Este archivo debería de contener lo siguiente:

```json
{
    "owner": {
        "username": "tu-usuario-de-github",
        "email": "tu-email@gmail.com"
    },
    "record": {
        "CNAME": "tu-nombre-de-sitio.pages.dev"
    }
}
```

### Tu sitio ya debería estar funcional!

Si has seguido todos los pasos correctamente, entonces tu sitio debería estar en línea después de que tu pull request haya sido procesada.
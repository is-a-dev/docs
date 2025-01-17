---
icon: /media/render.svg
label: Render
tags:
    - guides
    - spanish
---

# Configurando Render con un subdominio is-a.dev

Esta guía te guiará a través del proceso de configuración de un despliegue de Render y asignarle tu subdominio is-a.dev.

## Crear un servicio en Render

Primero, necesitarás crear un servicio en Render. Sigue las instrucciones en la [Documentación de Render](https://docs.render.com/).

### Crear el archivo de dominio

Crea un archivo JSON dentro del directorio `domains` (`domains/subdominio.json`) con el siguiente contenido y envía una pull request:

```json
{
    "description": "Describe el uso de este subdominio",
    "repo": "https://github.com/usuario-github/repositorio-github",
    "owner": {
        "username": "usuario-github",
        "email": "yo@ejemplo.com"
    },
    "record": {
        "A": ["216.24.57.1"]
    }
}
```

**Nota:** En la sección owner, puedes añadir cualquier red social, como Discord. Si añades otra cuenta de red social, puedes omitir el campo email. Sin embargo, el nombre de usuario de GitHub es obligatorio. No olvides proporcionar una vista previa de tu sitio en tu pull request.

## Configurando Render

- Después de que la pull request sea fusionada, necesitarás configurar tu servicio de Render para usar el nuevo subdominio. Ve al panel de control de servicio en Render.
- Navega a **Configuración > Dominios Personalizados** y añade  `subdominio.is-a.dev` en el campo proporcionado.
- Render proporcionará un paso de verificación, generalmente requiriendo que añadas un registro DNS. Este paso debe omitirse si tu subdominio ya está apuntando a la dirección IP de Render (`216.24.57.1`).

### Pasos Finales

- Espera a que los cambios de DNS se propaguen. Esto puede tomar desde unos minutos hasta un par de horas.
- Tu servicio de Render ahora debería ser accesible en `subdomain.is-a.dev`.

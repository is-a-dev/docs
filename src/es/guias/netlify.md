---
icon: /media/netlify.svg
label: Netlify
tags:
    - guides
    - spanish
---

# Configurando Netlify con un subdominio is-a.dev

Esta guía te guiará a través del proceso de configuración de un despliegue de Netlify y asignarle tu subdominio is-a.dev.

## Crear un sitio en Netlify

Primero, necesitarás crear un sitio en Netlify. Sigue las instrucciones en la [Documentación de Netlify](https://docs.netlify.com/).

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
        "A": ["75.2.60.5"]
    }
}
```

**Nota:** En la sección owner, puedes añadir cualquier red social, como Discord. Si añades otra cuenta de red social, puedes omitir el campo email. Sin embargo, el nombre de usuario de GitHub es obligatorio. No olvides proporcionar una vista previa de tu sitio en tu pull request.

## Configurando Netlify

- Después de que la pull request sea fusionada, necesitarás configurar tu sitio de Netlify para usar el nuevo subdominio. Ve al panel de control de tu sitio en Netlify.
- Navega a **Configuración del Sitio > Gestión de Dominios > Dominios Personalizados** y añade `subdominio.is-a.dev` en el campo proporcionado.
- Netlify proporcionará un paso de verificación, generalmente requiriendo que añadas un registro DNS. Este paso debe omitirse si tu subdominio ya está apuntando a la dirección IP de Netlify (`75.2.60.5`).

### Pasos Finales

- Espera a que los cambios de DNS se propaguen. Esto puede tomar desde unos minutos hasta un par de horas.
- Tu sitio de Netlify ahora debería ser accesible en `subdominio.is-a.dev`.

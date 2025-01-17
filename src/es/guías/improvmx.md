---
label: ImprovMX
icon: /media/improvmx.svg
tags:
    - guides
    - spanish
---

# Configurando ImprovMX con un subdominio is-a.dev

Esta guía te guiará a través del proceso de configuración de ImprovMX con tu subdominio is-a.dev.

## Lo que necesitas hacer antes de continuar

1. Tener una cuenta de ImprovMX. Si no tienes una cuenta de ImprovMX, visita [su sitio web](https://improvmx.com) y crea una cuenta.
2. Ya deberías haber bifurcado el [repositorio is-a.dev](https://github.com/is-a-dev/register). Si no has bifurcado el repositorio, hazlo usando [este enlace](https://github.com/is-a-dev/register/fork).

## Creando el archivo

Primero ve a la bifurcación que has creado, luego ve al directorio `domains` y crea un archivo. El archivo debe nombrarse así: `subdominio.json`. (Reemplaza `subdominio` con el nombre del subdominio que deseas, por supuesto.)

Después de haber creado el archivo, debes poner esto en el archivo:
```json
{
    "owner": {
        "username": "usuario-github",
        "email": "yo@ejemplo.com"
    },
    "record": {
        "MX": ["mx1.improvmx.com", "mx2.improvmx.com"],
        "TXT": ["v=spf1 include:spf.improvmx.com ~all"]
    }
}
```

**Después de haber creado el archivo, debes hacer una pull request al [repositorio is-a.dev](https://github.com/is-a-dev/register).**

## Configuración

Después de que haya sido fusionado, debería ser reconocido automáticamente y comenzar a funcionar. Si no lo has configurado previamente, ve al [panel de control de ImprovMX](https://app.improvmx.com/) y añade el dominio allí.

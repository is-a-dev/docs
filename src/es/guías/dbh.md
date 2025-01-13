---
label: DanBot Hosting
icon: /media/dbh.png
tags:
    - guides
    - spanish
---

# Configurando DanBot Hosting con un subdominio is-a.dev

Esta guía te guiará a través del proceso de configuración de un sitio en DanBot Hosting y el asignarle tu subdominio is-a.dev.

## Obtener la IP del Proxy

Ejecuta el siguiente comando en el [servidor de Discord de DanBot Hosting](https://discord.gg/dbh) en el canal #commands.


```
dbh!server proxy
```

Recibirás una respuesta como esta:

![](../media/dbh_proxy/1.jpg)

Si tienes un plan gratuito, elige cualquier proxy de US o puedes usar el Proxy para Donadores en caso de ser Donador. Anota la dirección IP del proxy que elijas.

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
        "A": ["ip-del-proxy-aqui"]
    }
}
```

**Nota:** En la sección owner, puedes añadir cualquier red social, como Discord. Si añades otra cuenta de red social, puedes omitir el campo email. Sin embargo, el nombre de usuario de GitHub es obligatorio. No olvides proporcionar una vista previa de tu sitio en tu pull request.

## Configuración

Después de que la pull request sea fusionada, obtén tu ID de servidor ejecutando este comando:

```
dbh!server list
```

Recibirás una respuesta como esta:

![](../media/dbh_proxy/2.jpg)

Anota el ID del servidor, luego ejecuta el siguiente comando:


```
dbh!server proxy tu-subdominio.is-a.dev tuiddservidor
```
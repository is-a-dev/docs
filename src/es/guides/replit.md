---
icon: /media/replit.svg
label: Replit
tags:
    - guides
    - spanish
---

# Configurando Replit con tu subdominio is-a.dev

## Creando un proyecto

Sigue las instrucciones en la [Guía del Espacio de Trabajo de Replit](https://docs.replit.com/programming-ide/introduction-to-the-workspace#how-to-create-a-repl) sobre cómo crear un proyecto.

### Conecta tu repl a tu subdominio is-a.dev

Sigue las instrucciones en la [Guía de Dominios Personalizados de Replit](https://docs.replit.com/hosting/custom-domains#connecting-your-domain-to-your-repl).

Solo sigue la sección "Conectando tu dominio a tu repl", luego vuelve a esta guía para los siguientes pasos.

### Creando el archivo de dominio

Crea un archivo JSON dentro del directorio `domains` (`domains/subdominio.json`) con el siguiente contenido:

**Nota:** No añadas ningún registro TXT, incluso si Replit te indica que lo hagas.

```json
{
    "owner": {
        "username": "usuario-github",
        "email": "yo@ejemplo.com"
    },
    "record": {
        "CNAME": "siteid.id.repl.co"
    }
}
```

## Finalización

¡Una vez que tu pull request haya sido fusionada, deberías poder visitar tu nuevo subdominio is-a.dev conectado a tu sitio de Replit!

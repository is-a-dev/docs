---
icon: /media/vercel.svg
label: Vercel
tags:
    - guides
    - spanish
---

# Configurando Vercel con un subdominio is-a.dev

Esta guía te guiará a través del proceso de configuración de un sitio de Vercel y asignarle tu subdominio is-a.dev.

## Asegúrate de tener un sitio en Vercel

Si aún no tienes un sitio en Vercel, asegúrate de crear uno. Sigue las instrucciones en la [Documentación de Vercel](https://vercel.com/docs/getting-started-with-vercel).

### Creando los archivos de dominio

Primero, ve a tu panel de control de Vercel, luego a tu proyecto, después a Dominios Personalizados y coloca allí el subdominio is-a.dev que deseas.

**Necesitarás crear dos archivos para asegurar que este proceso funcione correctamente**. Los haremos en orden.

1. Crea un archivo para la verificación TXT de Vercel.
   Al conectar el dominio, se te mostrará una cadena de verificación TXT. Para crear el archivo para este, el registro TXT debe colocarse en `_vercel.subdominio.json` en el **directorio domains** (reemplaza subdominio con el dominio que deseas, por supuesto) y el archivo debe ser así (Puedes dejar el campo email en blanco siempre que tengas otra red social, pero **no elimines el campo**):

```json
{
    "owner": {
        "username": "inserta-tu-usuario-github-aqui",
        "email": "",
        "discord": "inserta-tu-ID-de-usuario-discord-aqui"
    },
    "record": {
        "TXT": "inserta-la-cadena-TXT-que-obtuviste-de-vercel-aqui"
    }
}
```

!!!
**_NO HAGAS UNA PULL REQUEST TODAVÍA_**, aún tenemos que crear otro archivo. Si hicieras una pull request en este momento, rechazaríamos tu dominio ya que estás intentando crear un subdominio anidado en un subdominio que aún no posees. Por favor, continúa con el siguiente paso.
!!!

2. Crea un archivo para el dominio principal.
    Ahora necesitas crear un archivo para el dominio principal, tenemos dos formas de hacerlo: registros CNAME y A. Tendremos dos archivos diferentes para estos y explicaremos qué restricciones o cosas necesitas hacer.

Crea `subdominio.json` en el **directorio domains** (reemplaza subdominio con el dominio que deseas, por supuesto) y coloca en el archivo uno de estos tipos:

**Registro CNAME**: Si estás usando un registro CNAME, no tienes que dar una vista previa ya que estás usando el sitio como CNAME, pero no puedes usar otros registros (Como registros MX y TXT). **Esta opción es ideal para aquellos que solo quieren usar su dominio para su sitio.**.

```json
{
    "owner": {
        "username": "inserta-tu-usuario-github-aqui",
        "email": "",
        "discord": "inserta-tu-ID-de-usuario-discord-aqui"
    },
    "record": {
        "CNAME": "nombredominio.vercel.app"
    }
}
```

**Registro A**: Si estás usando un registro A, necesitarás proporcionar una vista previa ya sea poniendo un enlace en la sección de comentarios de la PR, poniéndolo en la descripción, o proporcionando una captura de pantalla de tu sitio web. **Esta opción es ideal para aquellos que quieren usar su dominio tanto para su sitio como para correo.**.

```json
{
    "owner": {
        "username": "inserta-tu-usuario-github-aqui",
        "email": "",
        "discord": "inserta-tu-ID-de-usuario-discord-aqui"
    },
    "record": {
        "A": ["76.76.21.21"]
    }
}
```

### Haz tu pull request.

Una vez que hayas creado estos dos archivos, puedes hacer una pull request al [repositorio principal](https://github.com/is-a-dev/register). Luego tendrás que ser paciente hasta que se fusione. Si quieres tener la oportunidad de que tu PR se fusione más rápido, ¡únete a nuestro [Servidor de Discord!](https://discord.gg/is-a-dev-830872854677422150)

Cuando la pull request haya sido fusionada, tu sitio debería estar funcionando. Si todavía se redirige al sitio is-a.dev, limpia tu caché.

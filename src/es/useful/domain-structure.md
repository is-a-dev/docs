---
tags: útil
icon: file-code
label: Estructura del Dominio
---

# Estructura del Dominio
Para registrar un subdominio, necesitas crear un nuevo archivo JSON en el directorio `domains` a través de una pull request. Por ejemplo, para registrar `ejemplo.is-a.dev`, deberías crear un archivo llamado `ejemplo.json` en el directorio `domains`. La ruta completa sería `domains/ejemplo.json`.

## Nombre del Archivo

**Nota**: Puedes incluir `.` (puntos) en el nombre de tu archivo para registrar un sub-subdominio (por ejemplo, `blog.ejemplo.is-a.dev`). Sin embargo, cada segmento de tu subdominio debe cumplir con los siguientes criterios:

El nombre del archivo:

- Debe ser alfanumérico, en minúsculas, con guiones como separadores.
- Debe tener al menos 1 carácter.
- Debe tener una extensión de archivo `.json`.

### Ejemplos de Nombres de Archivos Inválidos
- `.json` (el nombre del archivo tiene menos de 1 carácter)
- `A.json` (el nombre del archivo contiene letras mayúsculas)
- `a..json` (el nombre del archivo contiene puntos consecutivos)
- `.a.json` (el nombre del archivo comienza con un punto)
- `a .json` (el nombre del archivo contiene un espacio)
- `a$.json` (el nombre del archivo contiene un carácter no alfanumérico)
- `a.json.json` (el nombre del archivo contiene más de una extensión `.json`)
- `a.is-a.dev.json` (el nombre del archivo contiene `.is-a.dev`)

### Ejemplos de Nombres de Archivos Válidos
Todos los nombres de archivos a continuación cumplen con todos los criterios. La razón entre paréntesis es solo un ejemplo de uno de los criterios que cumplen.

- `a.json` (al menos 1 carácter de longitud)
- `ejemplo.json` (alfanumérico y en minúsculas)
- `blog.ejemplo.json` (incluye puntos para registrar un sub-subdominio)
- `mi-blog.json` (usa guiones como separadores, lo cual es recomendable)

**NOTA:** Para evitar que una persona tenga un monopolio sobre subdominios de una letra, limitamos a todos a solo un subdominio de una letra.

### Ejemplo de Archivo JSON
`domains/docs.json`
```json
{
  "description": "Sitio de documentación para is-a.dev",
  "repo": "https://github.com/is-a-dev/docs",
  "owner": {
    "username": "is-a-dev",
    "email": "admin@is-a.dev"
  },
  "record": {
    "CNAME": "is-a.dev"
  }
}
```
## Estructura

### owner (requerido)
Necesitas especificar alguna información sobre ti aquí. Esto es para que puedas ser contactado si es necesario.
En el objeto owner, los campos username y email son obligatorios. Puedes agregar más información en este objeto si lo deseas.
```json
{
  "owner": {
    "username": "usuario-github"
  }
}
```

### description
Describe tu nombre de dominio y su uso. Esto es puramente para fines de documentación y es opcional.

### repo
Este es un enlace a tu repositorio de sitio web o tu cuenta de github. Esto es puramente para fines de documentación y es opcional.

### record (requerido)
Esta sección es donde especificas los registros DNS.

Puedes ver una lista de los tipos soportados [aquí](/faq/#which-records-are-supported).

A continuación se presentan algunos ejemplos para los tipos de registro dados:

- **CNAME** record: Este debe ser un nombre de host (`algo.tld`). No se puede usar en conjunto con ningún otro tipo de registro. Esto se utiliza típicamente para mapear tu dominio a un servidor específico.

```json
{
  "record": {
    "CNAME": "usuario-github.github.io"
  }
}
```

- **A** record: Este debe ser una lista de direcciones IPv4. Estas direcciones apuntan tu dominio a un servidor específico.

```json
{
  "record": {
    "A": [
      "192.0.2.1",
      "198.51.100.1",
      "203.0.113.1"
    ]
  }
}
```

- **AAAA** record: Este debe ser una lista de direcciones IPv6. Al igual que el registro A, estas direcciones apuntan tu dominio a un servidor específico.

```json
{
  "record": {
    "AAAA": [
      "2001:0db8:85a3:0000:0000:8a2e:0370:7334",
      "2001:0db8:85a3:0000:0000:8a2e:0370:7335",
      "2001:0db8:85a3:0000:0000:8a2e:0370:7336"
    ]
  }
}
```

- **URL** record: Esto redirige tu dominio a otra URL.

```json
{
  "record": {
    "URL": "https://ejemplo.com"
  }
}
```

- **MX** record: Este debe ser una lista de nombres de host. Estos nombres de host especifican los servidores de correo que manejan los correos electrónicos para tu dominio.

```json
{
  "record": {
    "MX": [
      "mx1.improvmx.com",
      "mx2.improvmx.com"
    ]
  }
}
```

- **TXT** record: Este puede ser una cadena única o una lista de cadenas. Los registros TXT se utilizan a menudo para diversos propósitos, como verificar la propiedad del dominio y garantizar la seguridad del correo electrónico.

```json
{
  "record": {
    "TXT": "¡Hola Mundo!"
  }
}
```

```json
{
  "record": {
    "TXT": ["¡Hola", "Mundo!"]
  }
}
```

- **NS** record: Este debe ser una lista de nombres de host. Estos nombres de host especifican los servidores DNS autoritativos para tu dominio.

```json
{
  "record": {
    "NS": [
      "ns1.example.com",
      "ns2.example.com"
    ]
  }
}
```

Nota: Por favor, consulta las [preguntas frecuentes](https://docs.is-a.dev/faq/) para aclaraciones sobre qué o quién permitimos para los registros NS. Si deseas un ejemplo sobre lo que queremos como razonamientos, puedes [revisar esta PR](https://github.com/is-a-dev/register/pull/16758).

- **SRV** record: Este debe ser una lista de registros de servicio. Cada registro especifica la prioridad, el peso, el puerto y el objetivo para un servicio en tu dominio. Los registros SRV se utilizan a menudo para servicios como VoIP, mensajería y más.

```json
{
  "record": {
    "SRV": [
      {
        "priority": 10,
        "weight": 5,
        "port": 8080,
        "target": "srv.example.com"
      },
      {
        "priority": 20,
        "weight": 10,
        "port": 9090,
        "target": "srv2.example.com"
      }
    ]
  }
}
```

- **CAA** record: Este debe ser una lista de registros de Autorización de Autoridad de Certificación (CAA). Cada registro especifica la autoridad permitida para emitir certificados SSL para tu dominio, con campos para `flags`, `tag` y `value`.

```json
{
  "record": {
    "CAA": [
      {
        "flags": 0,
        "tag": "issue",
        "value": "letsencrypt.org"
      },
      {
        "flags": 0,
        "tag": "issuewild",
        "value": "comodoca.com"
      }
    ]
  }
}
```

### proxied (*opcional*)
Habilita el proxy de Cloudflare para tu dominio. Desactivado por defecto. Para habilitarlo, agrega esta línea de código:

```json
"proxied": true
```

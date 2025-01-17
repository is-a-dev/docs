---
icon: /media/discord.svg
label: Verificación de Dominio Discord
tags:
    - guides
    - spanish
---

# Configurando la verificación de dominio Discord con tu dominio is-a.dev

## Obtén tu cadena de verificación

1. Abre tu aplicación de Discord y presiona `Ajustes`.
   ![](../media/discord/step_1.png)

1. Abre la sección `Conexiones`.
   ![](../media/discord/step_2.png)

1. Presiona el botón `Ver más`.
   ![](../media/discord/step_3.png)

1. Haz clic en el botón de dominio (el ícono del globo).
   ![](../media/discord/step_4.png)

1. En el campo que aparece, escribe tu nombre de dominio is-a.dev (por ejemplo, `ejemplo.is-a.dev`).
   ![](../media/discord/step_5.png)

1. Copia la cadena de verificación.
   ![](../media/discord/step_6.png)

### Crear el archivo de dominio

Crea un archivo JSON dentro del directorio `domains/` llamado `domains/_discord.ejemplo.json` con el siguiente contenido:

```json
{
    "owner": {
        "username": "usuario-github",
        "email": "correo@direccion"
    },
    "record": {
        "TXT": "cadena-de-verificacion-discord"
    }
}
```

## Configuración

Después de que tu pull request haya sido fusionada, repite los pasos para obtener la cadena de verificación y presiona el botón `Verificar`.
Si muestra algún error como `No se puede verificar tu dominio`, intenta esperar unos minutos (a veces hasta 24 horas) ya que el DNS podría no haberse actualizado aún.

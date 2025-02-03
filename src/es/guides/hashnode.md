---
icon: /media/hashnode.svg
label: Hashnode
tags:
    - guides
    - spanish
---

# Blog de Hashnode

Cuando creas tu blog de Hashnode, Hashnode te proporciona un subdominio `hashnode.dev`. Sin embargo, puedes usar tu propio subdominio `is-a.dev`.

En esta guía aprenderás cómo hacerlo.

---

1. Inicia sesión en tu cuenta de Hashnode.

1. Haz clic en tu **avatar** en la esquina inferior izquierda de la página en **escritorio** o en la esquina superior derecha en **móvil**.
   ![Feed de Hashnode](https://cdn.hashnode.com/res/hashnode/image/upload/v1614932849541/cBNDGKXMj.png?auto=compress)

1. Haz clic en la opción **Panel de Control del Blog** en el modal emergente para acceder al panel de control de tu blog.
   ![Feed de Hashnode](https://cdn.hashnode.com/res/hashnode/image/upload/v1614937218081/InvxVHXDy.png?auto=compress)

1. Navega a la pestaña **Dominio** e ingresa tu dominio sin el prefijo **www** o **https://** en el campo de texto proporcionado. Luego haz clic en el botón **Actualizar** para continuar.
   ![Pestaña de Dominio del Blog de Hashnode](https://cdn.hashnode.com/res/hashnode/image/upload/v1614937377176/0cwddAywO.png?auto=compress)

1. Ve a tu fork del repositorio `is-a-dev/register`, edita el archivo JSON de tu subdominio, asegúrate de eliminar cualquier registro antiguo, luego añade esto a la clave `record` y crea una PR:

```json
"CNAME": "hashnode.network"
```

## Configuración

Una vez completado, tu blog de Hashnode debería estar configurado para usar tu subdominio. Estos cambios podrían tardar desde 1 hora hasta 48 horas, así que ten paciencia. Lo más probable es que esté listo en una hora.

Una vez que el DNS se haya propagado, ¡podrás empezar a disfrutar de tu blog de Hashnode con tu elegante subdominio `.is-a.dev`!

## ¿Necesitas más ayuda?

Si encuentras algún problema o necesitas ayuda adicional, considera los siguientes recursos:

- [Guía de Mapeo de Dominio de Hashnode](https://support.hashnode.com/docs/mapping-domain/): Este artículo de soporte proporciona instrucciones detalladas sobre cómo mapear tu dominio en Hashnode.
- [Centro de Soporte de Hashnode](https://support.hashnode.com/): Para ayuda más general relacionada con Hashnode, visita su Centro de Soporte.

Ten en cuenta que is-a.dev no está afiliado con Hashnode. Si estás experimentando problemas con tu blog de Hashnode, busca ayuda a través de los canales de soporte de Hashnode. No podemos ayudar con problemas específicos de Hashnode.

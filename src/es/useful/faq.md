---
icon: question
label: Preguntas Frecuentes (FAQ)
tags: 
    - useful
    - spanish
---
# Preguntas Frecuentes (FAQ)

## ¿Qué registros son compatibles?

- A
- AAAA
- CAA
- CNAME
- DS
    - Nota: Estos solo pueden usarse en combinación con registros NS, que se usan para DNSSEC.
- MX
- NS
    - Nota: Estos solo se otorgan en casos específicos. Consulta [`¿Quién puede usar registros NS?`](#quién-puede-usar-registros-ns) para más información.
- SRV
- TXT
- URL
    - Nota: Estos registros usan Cloudflare para redirección, no es un tipo real de registro DNS.

## ¿Por qué mi dominio sigue redirigiendo al sitio web is-a-dev?
Esto generalmente ocurre debido a que el caché de tu navegador se vuelve inválido y [limpiar el caché de tu navegador](https://support.google.com/accounts/answer/32050) debería resolver este problema.

## ¿Puedo usar un registro CNAME con otros registros?
No puedes solicitar un subdominio ni enviar cambios que contengan un CNAME con otros registros (A, AAAA, MX, TXT, etc...)

## ¿Cuánto tiempo tardará en fusionarse mi PR?
Cuando nos ocupemos de ello. Siempre queremos que esperes lo menos posible. Pero los mantenedores no siempre pueden estar en línea. Tenemos escuela y trabajo, esto es solo un proyecto secundario. ¡Solo sé paciente y lo revisaremos tan pronto como sea posible! Para una oportunidad de revisión más rápida, envía tu PR en [#⁠pull-requests](https://discord.com/channels/830872854677422150/1130858271620726784) en nuestro [servidor de Discord](https://discord.gg/is-a-dev-830872854677422150).

## ¿Qué servicios soportan?
Soportamos casi todos los servicios, sin embargo, estos son los principales servicios que la gente usa con is-a.dev:

- Cloudflare Pages
- GitHub Pages
- Netlify
- Railway
- Vercel

## ¿Puedo crear subdominios anidados? (sub-subdominios)
¡Sí, puedes! Simplemente crea un archivo como `blog.ejemplo.json` y sigue las mismas pautas que seguirías al registrar `ejemplo.json`. Ten en cuenta que para tener `blog.ejemplo.is-a.dev`, debes ser propietario de `ejemplo.is-a.dev`.

## ¿Cómo puedo editar mi dominio?
Puedes editar el archivo JSON de tu dominio y enviar una pull request para editarlo.

## ¿Cómo puedo eliminar mi dominio?
Puedes eliminar el archivo JSON de tu dominio y enviar una pull request para eliminarlo.

## Sigo recibiendo un error SSL mientras uso GitHub Pages, ¿cómo lo soluciono?
Necesitas ir a la configuración de GitHub Pages en tu repositorio del sitio web (probablemente llamado algo como `nombre-usuario.github.io`) y asegurarte de que la opción `Enforce HTTPS` esté habilitada para evitar este error.

## ¿Puedo ser un mantenedor/unirme al equipo?
No, elegimos a mano a cada miembro de nuestro equipo. Puedes aumentar tus posibilidades de ser elegido ayudando a las personas en nuestros foros de ayuda.

## He filtrado accidentalmente información sensible en mi PR, ¿cómo puedo hacer que se elimine?
Si tu PR **no ha sido fusionada**, puedes enviar un correo a [security@is-a.dev](mailto:security@is-a.dev) o enviar un MD a [williamharrison en Discord](https://discord.com/users/853158265466257448). Si tu PR ya ha sido fusionada, lamentablemente no hay nada que podamos hacer.

## ¿Puedo usar mi dominio para un servidor de Minecraft?
Sí, puedes. Puedes usar un registro A combinado con un registro SRV para esto.

Consulta [este artículo](https://www.namecheap.com/support/knowledgebase/article.aspx/9765/2208/how-can-i-link-my-domain-name-to-a-minecraft-server) de Namecheap para obtener ayuda.

## ¿Quién puede usar registros NS?
Permitimos registros NS para las siguientes razones y casos de uso:

- Usuarios que requieren una zona privada, ya que están usando su dirección IP doméstica a través de **un registro `A` O `AAAA`** detrás de un servicio proxy como Cloudflare. **DEBES proporcionar evidencia de uso para que este razonamiento sea aprobado.**
- Cuando un servicio de terceros (por ejemplo, Aternos, Wix o Squarespace) exige registros NS específicos y no puedes gestionar registros DNS directamente bajo ese dominio. La aprobación requiere:
  - Documentación o evidencia del servicio de terceros que indique explícitamente este requisito.
  - Prueba de que ninguna configuración DNS alternativa (CNAME, registros A, etc.) puede lograr el mismo resultado.

No permitimos registros NS para:

- Configuraciones solo por conveniencia: Donde alternativas como registros A, AAAA o CNAME son suficientes.
- Propósitos no operativos: Configuraciones de vanidad, configuraciones estéticas o uso especulativo.
- Reclamos no verificables: Cualquier configuración que carezca de evidencia clara y concreta de necesidad.
- Configuraciones engañosas: Intentos de tergiversar la propiedad, engañar a usuarios o suplantar a otra entidad.
- Riesgos de seguridad: Configuraciones que introducen vulnerabilidades, como delegar a servidores no confiables o poco fiables.

***Nos reservamos el derecho de denegar registros NS a nuestra discreción, sin importar el razonamiento.***

## ¿Por qué son tan estrictos con los registros NS?
Tenemos que ser estrictos con a quién delegamos registros NS ya que permiten al usuario final hacer básicamente *lo que quiera* con su subdominio.

Como probablemente puedas imaginar, esto puede abrir la puerta a muchos abusos, por lo que no están disponibles libremente para todos.

Si pudiéramos, delegaríamos registros NS a todos los que los quisieran, sin embargo no vivimos en un mundo perfecto, así que desafortunadamente no podemos.

## ¿Cómo puedo hacer cambios en mi subdominio is-a.dev?
1. **Abre tu archivo JSON:** Navega al directorio `domains` en tu fork y abre el archivo JSON correspondiente a tu subdominio (`domains/subdominio.json`).
2. **Haz tus cambios:** Edita el archivo JSON (o elimínalo) para reflejar los cambios que quieres hacer.
3. **Confirma tus cambios:** Una vez que hayas hecho tus cambios, confírmalos en tu fork.
4. **Sube tus cambios:** Sube tus cambios a tu repositorio bifurcado en GitHub.
5. **Envía una Pull Request:** Ve a tu repositorio bifurcado en GitHub y abre una pull request.
6. **Espera a que tu PR sea fusionada:** Después de enviar tu pull request, espera a que sea revisada y fusionada. ¡Una vez que tu pull request haya sido fusionada, tus cambios deberían estar activos!

**Nota:** Asegúrate de monitorear tu PR para revisiones en caso de que se soliciten algunos cambios.

# STAR DRIVER 2.0 — Propuesta de digitalización

Proyecto de demostración comercial para la escuela de manejo STAR DRIVER, basado en una recreación de la web pública y en ideas de automatización de matrículas. **No es aún un sistema de producción.**

## Archivos

- `index.html`, `styles.css`, `app.js`: recreación de la página informativa.
- `demo.html`: prototipo interactivo independiente de reservas, vista del alumno y panel del administrador. Todos los importes, alumnos y métricas son ficticios.

## Cómo ver la demo

Abrir `demo.html` en un navegador, o acceder a `/demo.html` si el repositorio está desplegado como web estática. Se recomienda utilizarlo para enseñar el flujo al propietario, no para cobrar ni almacenar datos.

## Flujo propuesto para el producto real

1. El propietario define servicios, tarifas reales, horarios, instructores y cupos.
2. El alumno selecciona servicio, registra los datos imprescindibles y solicita una reserva.
3. El servidor crea un pedido único con importe calculado en el backend y vencimiento.
4. El alumno paga mediante una pasarela autorizada en Perú (p. ej., Culqi).
5. El backend **valida el webhook y verifica la operación contra el proveedor**, evitando duplicados.
6. Tras confirmación auténtica, el sistema registra el cobro, asigna el cupo y envía la notificación correspondiente.
7. El personal accede al panel con autenticación y permisos para administrar matrículas, clases y comprobantes.

## Módulos necesarios para construirlo

- Registro de alumnos: datos mínimos, consentimiento y reglas de privacidad.
- Calendario: cupos por instructor, vehículo, sede y duración; prevención de doble reserva.
- Pagos: llave privada solo en el servidor; webhooks verificables, idempotencia, estados y conciliación.
- Administración: roles de propietario, recepcionista e instructor; historial/auditoría.
- Notificaciones: confirmaciones por correo; WhatsApp solo con API y consentimiento adecuados.
- Informes: total de matrículas, pagos recibidos, horarios ocupados y cancelaciones.
- Gestión operativa: política de cambios, devoluciones, reprogramaciones y atención de incidencias.

## Pendiente para uso comercial

- Confirmar autorización de marca, fotografías, testimonios, contenido y dominio con la empresa.
- Confirmar catálogo, precios, horarios, instructores, reglas de reservas y comisiones del medio de pago.
- Contratar/activar cuenta de cobro **a nombre de la empresa**, probar y verificar flujos.
- Implementar base de datos, backend, gestión de usuarios y auditoría; pruebas de seguridad.
- Revisar la contratación y la política de privacidad bajo normativa peruana.
- Elegir hosting apto para uso comercial: el plan Hobby de Vercel está limitado a usos no comerciales.

## Limitaciones de la demo

`demo.html` funciona solo en el navegador; los botones simulan operaciones locales, no procesan pagos, no crean matrículas en una base de datos y no envían datos a servidores. Los importes y estadísticas son exclusivamente de ejemplo.

## Negocio y mantenimiento

El contrato comercial debería especificar alcance, entregables, propiedad del código, uso de marca, quién es dueño de las cuentas de dominio, pasarela y hosting, precio de implementación, mensualidad opcional de mantenimiento, costos externos, cronograma y criterios de aceptación.


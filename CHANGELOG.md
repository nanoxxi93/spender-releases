# Changelog

Lo que cambia en cada versión de Spender, para quien la usa. El formato sigue
[Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/) y las versiones, [SemVer](https://semver.org/lang/es/).

## [1.0.2] - 2026-09-24

Soluciona problemas de sincronización al editar registros sin conexión a internet.

### Corregido

- **La app ya no se queda procesando para siempre tras un cambio sin conexión.** Si editabas o borrabas un registro estando offline, al volver a conectarte se quedaba colgado con el icono de progreso y el servidor no lo actualizaba. Ahora los cambios se aplican y la sincronización termina correctamente.

## [1.0.1] — 2026-09-24

La sesión ya no se pierde por dejar la app unos días sin abrir.

### Corregido

- **Volver a la app tras varios días ya no manda al login.** Al abrirla se veían los datos y, al
  terminar de sincronizar, la app cerraba la sesión aunque siguiera siendo válida. Ahora la renueva
  sola y sigue donde estaba.
- **Un fallo pasajero ya no cierra la sesión.** Si la red se corta o el servidor tarda en responder
  justo al renovarla, la app conserva la sesión y los datos guardados, y lo vuelve a intentar más
  tarde. Solo pide entrar de nuevo si el servidor rechaza la sesión de verdad.
- **Cerrar la app a mitad de una renovación ya no cuesta la sesión**, siempre que se vuelva a abrir
  en menos de un día.
- **Los colores del gráfico de balance ya no se intercambian.** Ingresos y gastos tienen siempre su
  color, sea cual sea el mayor.

## [1.0.0] — 2026-09-12

Primera versión pública de la app Android, la misma que corre en
[spender.harima.top](https://spender.harima.top), empaquetada con Capacitor.

### Añadido

- **Gastos, ingresos y transferencias**, multi-moneda y con notas.
- **Cuentas** de efectivo, tarjeta, banco y cripto, con saldos y fechas de tarjeta.
- **Categorías y subcategorías, beneficiarios y proyectos.**
- **Transacciones programadas**: una vez, diaria, semanal, mensual o anual.
- **Gráficos** por categoría, subcategoría y cuenta; calendario; búsqueda y filtros.
- **Exportar a CSV** y calculadora integrada.
- **Desbloqueo por biometría** y **escaneo de boletas con OCR en el propio dispositivo**.
- **Uso sin red**, con sincronización en segundo plano.

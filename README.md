# Spender

App de finanzas personales: gastos, ingresos, transferencias, cuentas y reportes. Funciona **sin
red** y sincroniza sola cuando vuelve la conexión.

Este repositorio no tiene código: solo publica los APK firmados de la app Android. El código fuente
es privado.

### [⬇ Descargar la última versión](https://github.com/nanoxxi93/spender-releases/releases/latest)

¿Solo quieres probarla? La misma app corre en el navegador, sin instalar nada:
**[spender.harima.top](https://spender.harima.top)**

## Qué hace

- Movimientos de **gasto, ingreso y transferencia**, multi-moneda y con notas
- Cuentas de efectivo, tarjeta, banco y cripto, con saldos y fechas de tarjeta
- Categorías y subcategorías, beneficiarios y proyectos
- Transacciones programadas: una vez, diaria, semanal, mensual o anual
- Inicio con gráficos por categoría, subcategoría y cuenta; calendario; búsqueda y filtros
- Exportar a CSV y calculadora integrada

Y dos cosas que solo existen en el teléfono:

- **Desbloqueo por biometría**
- **Escanear boletas con la cámara**, con el OCR corriendo en el propio dispositivo

## Sin red

Las transacciones se guardan en el teléfono y cada cambio queda marcado como pendiente. Un proceso
en segundo plano sincroniza con el servidor cada minuto, en los dos sentidos. Los identificadores se
generan en el propio dispositivo, así que un movimiento anotado en el metro ya nace con su identidad
definitiva y no se duplica al subir.

El escaneo de boletas también funciona sin conexión: el motor de OCR viaja dentro del APK.

## Instalar

Requiere **Android 7.0 (API 24)** o superior, y una cuenta, que se crea desde la propia app.

1. Descarga el APK de la [última versión](https://github.com/nanoxxi93/spender-releases/releases/latest).
2. Al abrirlo, Android pedirá permiso para instalar aplicaciones de esa fuente.
3. **Play Protect puede avisar de que el desarrollador no se ha visto antes** y bloquear la primera
   vez. Es lo normal en una app que no viene de la tienda: al reintentar, deja instalar.

Si algún día Spender llega a Google Play, quien la haya instalado desde aquí tendrá que
**desinstalar antes** de instalar la de la tienda. No es un capricho: Google firma con su propia
clave las apps que distribuye, y Android no deja actualizar un paquete cambiándole la firma.

## Qué hace con tus datos

Es una app de dinero, así que conviene decirlo:

- **La foto de la boleta no se guarda ni se sube.** El OCR corre en el dispositivo y solo se queda
  el texto que reconoce.
- **La biometría no sale del teléfono**: la comprueba Android, la app solo recibe el sí o el no.
- **Los tokens de sesión no viajan a la copia de seguridad de Google Drive.**
- **Los saldos no aparecen en la vista de apps recientes ni en las capturas de pantalla.**

## Verificar lo que descargaste

Cada versión publica el SHA-256 de su APK en las notas. Para comprobarlo:

```bash
sha256sum spender-1.0.0.apk
```

En Windows, `certutil -hashfile spender-1.0.0.apk SHA256`.

Y para confirmar quién firmó el paquete, con las herramientas del SDK de Android:

```bash
apksigner verify --print-certs spender-1.0.0.apk
```

La huella del certificado es la misma en todas las versiones, y es esta:

```
F0:48:2E:D2:5D:7A:1A:F8:E1:62:F3:A3:46:E6:97:E2:88:84:E0:05:36:6E:22:43:A5:D2:25:0F:EF:EC:A4:ED
```

Si no coincide, el archivo no salió de aquí.

## Licencia

Software propietario: se publica el binario, no el código. Puedes instalarlo y usarlo, y
redistribuir el APK sin modificar. Los detalles, en [LICENSE](LICENSE).

El uso del servicio —cuenta, sincronización y planes de pago— se rige por los Términos y
Condiciones y la Política de Privacidad que la propia app muestra al registrarte.

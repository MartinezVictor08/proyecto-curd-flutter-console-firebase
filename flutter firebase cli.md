Para integrar Firebase con Flutter de manera profesional, el uso de **Firebase CLI** es fundamental. Este permite automatizar la configuración y sincronizar tus archivos de `firebase_options.dart` sin errores manuales.

---

## 1. Software Necesario: Node.js y npm

Para instalar Firebase CLI, el motor principal es **Node.js**, el cual incluye automáticamente **npm** (Node Package Manager).

### Cómo verificar si ya están instalados
Antes de descargar nada, abre tu terminal (CMD, PowerShell o Terminal de macOS) y ejecuta:

* **Para Node.js:** `node -v`
* **Para npm:** `npm -v`

> Si obtienes un número de versión (ej. `v20.10.0`), ya estás listo. Si recibes un error de "comando no encontrado", sigue los pasos de instalación.

---

## 2. Instalación de Node.js y npm (Paso a paso)

Si no lo tienes, la forma más estable es descargar el instalador oficial:

1.  **Descarga:** Ve a [nodejs.org](https://nodejs.org/) y selecciona la versión **LTS** (Long Term Support). Es la más recomendada para evitar errores de compatibilidad.
2.  **Ejecución:** Abre el instalador descargado.
3.  **Configuración:** Sigue los pasos del asistente. Asegúrate de que la casilla **"Add to PATH"** esté marcada (esto permite que los comandos funcionen de manera global).
4.  **Finalización:** Al terminar, **reinicia tu terminal** para que reconozca las nuevas rutas.

---

## 3. Instalación de Firebase CLI de manera Global

Una vez que `npm` funciona, instalaremos las herramientas de Firebase para que estén disponibles en cualquier carpeta de tu computadora.

Ejecuta el siguiente comando:

```bash
npm install -g firebase-tools
```

* **-g:** Significa "global", permitiéndote usar el comando `firebase` en cualquier proyecto.

---

## 4. Acceso a Firebase con tu Cuenta de Google

Para que la CLI tenga permiso de modificar tus proyectos en la consola, debes autenticarte:

1.  En la terminal, escribe:
    ```bash
    firebase login
    ```
2.  **¿Permitir recopilación de información?** Escribe `Y` o `n` según tu preferencia.
3.  **Navegador:** Se abrirá automáticamente una ventana en tu navegador. Selecciona la cuenta de Google donde tienes tus proyectos de Firebase.
4.  **Confirmación:** Una vez aceptado, la terminal mostrará un mensaje de éxito: `Success! Logged in as tu-email@gmail.com`.

---

## 5. Comandos Esenciales de `firebase-tools`

Aquí tienes los comandos que más usarás trabajando con Flutter:

| Comando | Propósito |
| :--- | :--- |
| `firebase projects:list` | Lista todos los proyectos que tienes en la consola de Firebase. |
| `firebase login:logout` | Cierra la sesión actual en la CLI. |
| `firebase init` | Inicia la configuración de servicios (Hosting, Firestore, etc.) en tu carpeta actual. |
| `firebase help` | Muestra una lista detallada de todos los comandos disponibles. |

---

### Paso extra para Flutter: FlutterFire CLI
Ya que mencionas Flutter, después de tener Firebase CLI, el siguiente paso lógico es instalar el activador para Flutter:

```bash
dart pub global activate flutterfire_cli
```

Luego, dentro de la raíz de tu proyecto Flutter, ejecutas `flutterfire configure` para vincularlo todo automáticamente. 

¿Ya tienes creado tu proyecto en la Firebase Console o necesitas ayuda para vincular el ID del proyecto con el código de Flutter?

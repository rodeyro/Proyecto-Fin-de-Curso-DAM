# Manual de Instalación

## Introducción

Este documento proporciona los pasos para instalar y ejecutar dos APKs en dos dispositivos móviles diferentes utilizando Android Studio. Se asume que ya tienes los archivos APK listos en tu ordenador.

## Requisitos

- Android Studio instalado y configurado.
- Dos dispositivos móviles con **depuración USB** habilitada.
- Cables USB para conectar los dispositivos al ordenador.
- Archivos APK proporcionados: `app1-release.apk` y `app2-release.apk`.

## 1. Configuración Inicial

### Habilitar la Depuración USB en los Dispositivos

1. Abre **Configuración** en cada dispositivo móvil.
2. Ve a **Opciones de desarrollador**.
3. Activa **Depuración USB**.

### Conectar los Dispositivos

Conecta ambos dispositivos a tu ordenador utilizando cables USB.

## 2. Verificación de Conexiones

### Comprobar la Conexión con `adb`

1. Abre una terminal o el símbolo del sistema.
2. Ejecuta el siguiente comando para listar los dispositivos conectados:

    ```bash
    adb devices
    ```

Deberías ver una lista de dispositivos con sus identificadores. Asegúrate de que ambos dispositivos estén listados.

## 3. Instalar las APKs

### Usando Android Studio

1. Abre Android Studio.
2. Ve a **View** > **Tool Windows** > **Device File Explorer**.
3. Encuentra ambos dispositivos en la lista.

#### Instalación en el Primer Dispositivo

1. Selecciona el primer dispositivo en el desplegable de la barra de tareas.
2. Arrastra y suelta `app1-release.apk` desde tu explorador de archivos a la ventana de **Device File Explorer**.
3. O, usa la opción **Run** desde el menú de **Build** para instalar manualmente:
    - Ve a **Build** > **Build APK(s)** y selecciona la opción para instalar el APK.

#### Instalación en el Segundo Dispositivo

1. Cambia al segundo dispositivo en el desplegable de la barra de tareas.
2. Arrastra y suelta `app2-release.apk` a la ventana de **Device File Explorer**.
3. O, instala manualmente usando **Build** > **Build APK(s)** y selecciona la opción para instalar el APK.

### Usando la Línea de Comandos

1. Abre una terminal o el símbolo del sistema.
2. Navega al directorio donde están almacenadas las APKs.

#### Instalación en el Primer Dispositivo

3. Ejecuta el siguiente comando, reemplazando `<ID_dispositivo_1>` por el identificador del primer dispositivo y `app1-release.apk` por el nombre del archivo APK correspondiente:

    ```bash
    adb -s <ID_dispositivo_1> install -r app1-release.apk
    ```

#### Instalación en el Segundo Dispositivo

4. Ejecuta el siguiente comando, reemplazando `<ID_dispositivo_2>` por el identificador del segundo dispositivo y `app2-release.apk` por el nombre del archivo APK correspondiente:

    ```bash
    adb -s <ID_dispositivo_2> install -r app2-release.apk
    ```

## 4. Ejecución de las Aplicaciones

- Desbloquea ambos dispositivos.
- Encuentra la aplicación instalada en cada dispositivo (puede tener nombres o íconos diferentes).
- Toca para abrir la aplicación en cada dispositivo.

## 5. Resolución de Problemas

Si encuentras problemas al instalar o ejecutar las APKs:

- Verifica que la depuración USB esté habilitada en ambos dispositivos.
- Asegúrate de que los IDs de los dispositivos sean correctos en el comando `adb`.
- Si la instalación falla, intenta desinstalar cualquier versión anterior de la aplicación en los dispositivos y vuelve a intentar.
- Consulta los logs de `adb` con:

    ```bash
    adb logcat
    ```

## Contribuciones

Si encuentras problemas o tienes sugerencias, por favor abre un issue o una pull request.

## Licencia

Este proyecto está licenciado bajo la [Licencia MIT](https://es.wikipedia.org/wiki/Licencia_MIT).

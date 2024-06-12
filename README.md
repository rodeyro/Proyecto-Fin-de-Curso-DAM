# Manual de Instalación

## Introducción

Este documento proporciona los pasos para descargar, transferir e instalar dos APKs desde un repositorio de GitHub a dos dispositivos móviles diferentes.

## Requisitos

- Dos dispositivos móviles con [**depuración USB**](https://developer.android.com/codelabs/basic-android-kotlin-compose-connect-device?hl=es-419#0) habilitada.
- Cables USB para conectar los dispositivos al ordenador.
- [ADB (Android Debug Bridge)](https://developer.android.com/studio/command-line/adb) instalado (opcional para instalación manual).
- Archivos APK disponibles en este repositorio:
  - [`app1-release.apk`](./path/to/app1-release.apk)
  - [`app2-release.apk`](./path/to/app2-release.apk)

## 1. Descargar los APKs desde GitHub

1. Ve a la sección [Releases](./releases) de este repositorio en GitHub.
2. Descarga los archivos APK:
   - [`app1-release.apk`](./path/to/app1-release.apk)
   - [`app2-release.apk`](./path/to/app2-release.apk)

## 2. Transferencia a los Dispositivos

### Usando Conexión USB

1. Conecta cada dispositivo móvil a tu ordenador utilizando cables USB.
2. Copia `app1-release.apk` y `app2-release.apk` a la carpeta **Descargas** o cualquier otra carpeta accesible en los dispositivos.

### Usando Almacenamiento en la Nube (Alternativa)

1. Sube `app1-release.apk` y `app2-release.apk` a un servicio de almacenamiento en la nube (como Google Drive, Dropbox, etc.).
2. En los dispositivos móviles, abre el enlace a los archivos APK en tu navegador.
3. Descarga los APKs en la carpeta **Descargas** o cualquier otra ubicación accesible.

## 3. Instalación de los APKs en los Dispositivos

### Instalación Manual en los Dispositivos

1. En cada dispositivo, navega hasta la carpeta donde se copiaron o descargaron los archivos APK.
2. Toca en `app1-release.apk` para el primer dispositivo y en `app2-release.apk` para el segundo dispositivo.
3. Sigue las instrucciones en pantalla para completar la instalación.

**Nota**: Es posible que necesites habilitar la instalación de aplicaciones de fuentes desconocidas en los dispositivos. Esto puede hacerse en **Configuración** > **Seguridad** > **Instalar aplicaciones desconocidas**.

### Usando `adb` (Opcional)

Si prefieres usar `adb` para instalar los APKs:

1. Abre una terminal o el símbolo del sistema.
2. Navega al directorio donde están almacenadas las APKs descargadas.

#### Instalación en el Primer Dispositivo

3. Ejecuta el siguiente comando, reemplazando `<ID_dispositivo_1>` por el identificador del primer dispositivo y `app1-release.apk` por el nombre del archivo APK correspondiente:

    ```bash
    adb -s <ID_dispositivo_1> install -r path/to/app1-release.apk
    ```

#### Instalación en el Segundo Dispositivo

4. Ejecuta el siguiente comando, reemplazando `<ID_dispositivo_2>` por el identificador del segundo dispositivo y `app2-release.apk` por el nombre del archivo APK correspondiente:

    ```bash
    adb -s <ID_dispositivo_2> install -r path/to/app2-release.apk
    ```

## 4. Ejecución de las Aplicaciones

- Desbloquea ambos dispositivos.
- Encuentra la aplicación instalada en cada dispositivo (puede tener nombres o íconos diferentes).
- Toca para abrir la aplicación en cada dispositivo.

## 5. Resolución de Problemas

Si encuentras problemas al instalar o ejecutar las APKs:

- Verifica que la instalación de aplicaciones de fuentes desconocidas esté permitida.
- Asegúrate de que los IDs de los dispositivos sean correctos en el comando `adb` si usas esta herramienta.
- Si la instalación falla, intenta desinstalar cualquier versión anterior de la aplicación en los dispositivos y vuelve a intentar.
- Consulta los logs de `adb` con:

    ```bash
    adb logcat
    ```

## Contribuciones

Si encuentras problemas o tienes sugerencias, por favor abre un issue o una pull request.

## Licencia

Este proyecto está licenciado bajo la [Licencia MIT](https://es.wikipedia.org/wiki/Licencia_MIT).

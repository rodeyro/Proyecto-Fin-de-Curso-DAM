#  Manual de Instalación

## Cómo ejecutar dos APKs en diferentes móviles desde Android Studio

### Requisitos Previos

- Android Studio instalado.
- Proyecto de Android configurado.
- Dos dispositivos móviles o emuladores.

### 1. Configuración Inicial

Asegúrate de que cada dispositivo móvil tenga habilitada la **depuración USB**:

1. Abre **Configuración** en el dispositivo.
2. Ve a **Opciones de desarrollador**.
3. Activa **Depuración USB**.

Conecta ambos dispositivos a tu computadora mediante USB.

### 2. Configuración del Proyecto

#### Configuración del Variants Build

Si necesitas generar dos APKs diferentes, puedes configurar variantes de build.

1. Abre el archivo `build.gradle` del módulo de la aplicación.
2. Agrega configuraciones específicas para cada variante. Por ejemplo:

    ```groovy
    android {
        ...
        productFlavors {
            flavor1 {
                applicationId "com.example.app.flavor1"
                versionName "1.0-flavor1"
                ...
            }
            flavor2 {
                applicationId "com.example.app.flavor2"
                versionName "1.0-flavor2"
                ...
            }
        }
    }
    ```

### 3. Generar APKs

1. Selecciona la variante de build que deseas construir para el primer móvil desde la barra de tareas de Android Studio.
2. Construye el APK:
    - Ve a **Build** > **Build Bundle(s) / APK(s)** > **Build APK(s)**.
    - Encuentra el APK generado en el directorio `app/build/outputs/apk/flavor1/`.

3. Repite el proceso para la segunda variante y encuentra el APK en `app/build/outputs/apk/flavor2/`.

### 4. Firmar las APKs

Antes de distribuir las APKs, deben estar firmadas.

1. Ve a **Build** > **Generate Signed Bundle / APK**.
2. Selecciona **APK** y sigue las instrucciones del asistente:
    - Elige la variante de build (flavor1 o flavor2).
    - Proporciona la clave de firma y la contraseña.
    - Firma la APK.
3. Guarda el APK firmado en una ubicación deseada.

### 5. Instalar las APKs

#### Usando Android Studio

1. Conecta el primer dispositivo.
2. Selecciona el dispositivo desde la lista desplegable de dispositivos conectados.
3. Ejecuta la aplicación con la variante correspondiente.
4. Repite el proceso para el segundo dispositivo.

#### Usando la Línea de Comandos

1. Abre un terminal.
2. Navega al directorio donde se encuentra la APK firmada.
3. Usa `adb` para instalar la APK:

    ```bash
    adb -s <ID_dispositivo_1> install -r app-flavor1-release.apk
    adb -s <ID_dispositivo_2> install -r app-flavor2-release.apk
    ```

    Donde `<ID_dispositivo_1>` y `<ID_dispositivo_2>` son los identificadores únicos de tus dispositivos, que puedes obtener con `adb devices`.

### 6. Ejecución en Dispositivos

- Desbloquea ambos dispositivos.
- Encuentra la aplicación instalada (puede tener nombres o íconos diferentes según la configuración).
- Lanza la aplicación.

### 7. Resolución de Problemas

Si encuentras problemas al instalar o ejecutar las APKs:

- Verifica que la depuración USB esté habilitada en ambos dispositivos.
- Asegúrate de que el ID del dispositivo esté correcto en el comando `adb`.
- Consulta el log de Android Studio o `adb logcat` para errores detallados.

## Contribuciones

Si encuentras problemas o tienes sugerencias, por favor abre un issue o una pull request.

## Licencia

Este proyecto está licenciado bajo la [Licencia MIT](LICENSE).

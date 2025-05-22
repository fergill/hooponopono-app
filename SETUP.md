# Configuración del Entorno de Desarrollo

## Requisitos Previos

- Java Development Kit (JDK) 8 o superior
- Android Studio (última versión recomendada)
- Maven
- Git
- Cuenta de Firebase (para pruebas de base de datos y almacenamiento)
- Conexión a Internet

## Pasos para la Configuración

1. **Inicializa el repositorio en tu carpeta local del proyecto (si no existe):**
   ```sh
   git init
   ```

2. **Añade todos los archivos nuevos y cambios:**
   ```sh
   git add .
   ```

3. **Haz un commit:**
   ```sh
   git commit -m "Añadir archivos iniciales"
   ```

4. **Añade el repositorio remoto (solo si no está configurado):**
   ```sh
   git remote add origin https://github.com/fergill/hooponopono-app.git
   ```

5. **Sube los archivos a la rama principal:**
   ```sh
   git push -u origin main
   ```

6. **(Opcional) Si ya tienes archivos en remoto y quieres traerlos primero:**
   ```sh
   git pull origin main --allow-unrelated-histories
   ```

7. **Clonar el repositorio**
   ```sh
   git clone https://github.com/fergill/hooponopono-app.git
   cd hooponopono-app
   ```

8. **Abrir el proyecto en Android Studio**
   - Selecciona "Open an existing project" y elige la carpeta del repositorio clonado.

9. **Configurar Maven**
   - Asegúrate de tener Maven instalado (`mvn -v`).
   - El proyecto incluye un archivo `pom.xml` para la gestión de dependencias y el build.
   - Para compilar y construir el proyecto, ejecuta:
     ```sh
     mvn clean install
     ```

10. **Configurar Firebase**
    - Crea un proyecto en [Firebase Console](https://console.firebase.google.com/).
    - Descarga el archivo `google-services.json` y colócalo en `app/`.
    - Habilita Firebase Realtime Database y Cloud Storage.

11. **Instalar dependencias**
    - Android Studio y Maven gestionarán las dependencias automáticamente.

12. **Configurar emulador o dispositivo físico**
    - Configura un emulador Android o conecta un dispositivo físico para pruebas.

13. **Ejecutar la aplicación**
    - Haz clic en "Run" en Android Studio o usa `Shift + F10`.
    - También puedes usar Maven para ejecutar tareas específicas.

14. **Integrar SonarCloud (opcional pero recomendado)**
    - Crea una cuenta en [SonarCloud](https://sonarcloud.io/) y vincula tu repositorio.
    - Instala el plugin de SonarLint en Android Studio para análisis local.
    - Añade el archivo `sonar-project.properties` en la raíz del proyecto con la configuración básica:
      ```
      sonar.organization=tu-organizacion
      sonar.projectKey=tu-proyecto
      sonar.host.url=https://sonarcloud.io
      sonar.login=tu-token
      ```
    - Configura tu CI (por ejemplo, GitHub Actions) para ejecutar el análisis de SonarCloud en cada push/pull request. Consulta la [documentación oficial](https://docs.sonarcloud.io/advanced-setup/ci-based-analysis/) para detalles.

15. **Integrar GitHub Actions**
    - Crea el archivo `.github/workflows/ci.yml` en la raíz del repositorio con la configuración básica para proyectos Java/Android.
    - GitHub Actions ejecutará automáticamente los tests y builds definidos en el archivo de configuración en cada push o pull request.

## ¿Cómo subir todos los ficheros al repositorio de GitHub?

1. Inicializa el repositorio (si no existe):
   ```sh
   git init
   ```

2. Añade todos los archivos nuevos y cambios:
   ```sh
   git add .
   ```

3. Haz un commit:
   ```sh
   git commit -m "Añadir archivos iniciales"
   ```

4. Añade el repositorio remoto (solo si no está configurado):
   ```sh
   git remote add origin https://github.com/fergill/hooponopono-app.git
   ```

5. Sube los archivos a la rama principal:
   ```sh
   git push -u origin main
   ```

6. (Opcional) Si ya tienes archivos en remoto y quieres traerlos primero:
   ```sh
   git pull origin main --allow-unrelated-histories
   ```

## ¿Cómo autenticarte en GitHub desde la terminal?

1. Si usas HTTPS, genera un [Personal Access Token](https://github.com/settings/tokens) y úsalo como contraseña cuando Git te lo pida.
2. O bien, configura SSH:

   ```sh
   ssh-keygen -t ed25519 -C "tu-email@ejemplo.com"
   # Presiona Enter para aceptar la ubicación por defecto y pon una passphrase si quieres
   cat ~/.ssh/id_ed25519.pub
   # Copia la clave pública y añádela en GitHub: Settings > SSH and GPG keys > New SSH key
   git remote set-url origin git@github.com:fergill/hooponopono-app.git
   ```

3. Para comprobar la conexión SSH:
   ```sh
   ssh -T git@github.com
   ```

## Descripción para el repositorio GitHub

App Android para practicar Ho'oponopono con contador, grabación e historial.

## Notas

- Utiliza ramas para nuevas funcionalidades y realiza pull requests para revisión.
- Consulta el archivo `LICENSE` para información sobre el uso del código.

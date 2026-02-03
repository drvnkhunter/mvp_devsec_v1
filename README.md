# 🏦 Banca Móvil Secure - Backend Core (v0.1 - POC)

![Kotlin](https://img.shields.io/badge/Kotlin-1.9-purple?logo=kotlin)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-green?logo=springboot)
![Tomcat](https://img.shields.io/badge/Server-Tomcat_Embedded-orange)

> **Prueba de Concepto (POC): Inicialización de Arquitectura Segura.**
> Este repositorio contiene la configuración inicial del **Backend** para el proyecto de Banca Móvil. El objetivo de esta fase es validar el entorno de ejecución, el contenedor de servlets embebido (Tomcat) y la exposición del primer Endpoint REST.

---

## 🏗 Estado Actual del Proyecto (Fase 1)

Se ha completado la configuración del entorno "Server-Side" con las siguientes características:

1.  **Motor:** Configuración de **Spring Boot 3** con **Kotlin**.
2.  **Servidor:** Implementación de **Apache Tomcat 10 (Embebido)** para despliegue mediante JAR.
3.  **API REST:** Creación del primer controlador (`SaludoController`) para validar conectividad HTTP.
4.  **Gestor de Dependencias:** Maven configurado para futuras librerías de seguridad.

---

## 🛠 Stack Tecnológico Confirmado

| Componente | Selección | Estatus |
| :--- | :--- | :--- |
| **Lenguaje** | Kotlin (JDK 17) | ✅ Implementado |
| **Framework** | Spring Boot 3 (Web) | ✅ Implementado |
| **Despliegue** | Archivo .JAR (Standalone) | ✅ Configurado |
| **Base de Datos** | MySQL | 🔄 En Proceso de Integración |
| **Cliente Móvil** | Flutter | 🔄 En Proceso de Integración |

---

## 📋 Guía de Ejecución (Cómo probar este avance)

Para ejecutar este código, el evaluador necesita tener instalado:

* **Java JDK 17** (Versión LTS).
* **IntelliJ IDEA Community** (Para ejecutar el Backend).
* **Flutter SDK** y **Android Studio** (Para el emulador móvil).
* **XAMPP** (Para la base de datos MySQL).

---

## 🚀 Guía de Ejecución Paso a Paso

Sigue estas instrucciones para levantar el sistema tal como fue desarrollado.

### PASO 1: Ejecutar el Backend (Servidor)
*El servidor se gestiona desde el entorno visual de IntelliJ IDEA.*

1.  Abre **IntelliJ IDEA**.
2.  Selecciona **File > Open** y busca la carpeta `/backend` de este repositorio.
3.  Espera a que termine la indexación (barra inferior derecha).
4.  En el menú lateral izquierdo, navega a:
    `src` > `main` > `kotlin` > `com.banco.backend` > **`BackendApplication.kt`**
5.  Da **Clic Derecho** sobre el archivo y selecciona **Run 'BackendApplication'**.
6.  **Confirmación:** En la consola inferior verás el mensaje:
    `Tomcat started on port(s): 8080 (http)`

### PASO 2: Validar el Endpoint (Prueba de Vida)
Antes de abrir la app, verifica que el servidor responde. Abre tu navegador y ve a:

👉 `http://localhost:8080/hola`

**Debes ver este JSON:**
```json
{
  "status": "OK",
  "mensaje": "Hola Profe, el Backend con Kotlin está funcionando",
  "tecnologia": "Tomcat Embebido + Spring Boot"
}
```

### 3. Ejecutar el Frontend (App Móvil)
La aplicación móvil consume el servicio anterior.
1.  Abre una terminal (o VS Code) en la carpeta /frontend.
2.  Asegúrate de tener un emulador de Android abierto.
3.  Ejecuta el comando:

```Bash
# Instalar dependencias
flutter pub get

# Ejecutar en Emulador Android
flutter run
```
4.  La aplicación se instalará en el emulador.
- Nota: La app está configurada para apuntar a 10.0.2.2:8080 (que es la dirección IP especial para que el emulador vea al localhost de la PC).

---

## 🔒 Estado de Funcionalidades

- ✅ **Backend:** Servidor Tomcat Embebido - Completado
- ✅ **Backend:** Endpoint de Prueba (REST) - Completado
- ✅ **Frontend:** Pantalla de Login - Completado
- 🔄 **Seguridad:** Autenticación JWT - Pendiente (Fase 2)
- 🔄 **Frontend:** Conexión HTTP al Backend - Pendiente

---

## 🔮 Siguientes Pasos (Fase 2 - Hardening)

Una vez validada la conectividad básica, se procederá a:
1.  Implementar **Spring Security** para proteger los endpoints.
2.  Cifrar contraseñas con **BCrypt** en la base de datos.
3.  Generar el reporte de escaneo de vulnerabilidades (**Veracode**).

---

**Daniel Cunjamá**  
Máster en Ciberseguridad

***

```text
# Archivos de compilación y temporales
/target/
/build/
.idea/
.vscode/
*.iml
*.log
.DS_Store

# Flutter
/frontend/build/
/frontend/.dart_tool/
/frontend/.pub/
```

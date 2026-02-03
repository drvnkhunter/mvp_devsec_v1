# 🏦 Banca Móvil Secure - MVP

![Kotlin](https://img.shields.io/badge/Kotlin-1.9-purple?logo=kotlin)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-green?logo=springboot)
![Flutter](https://img.shields.io/badge/Flutter-3.x-blue?logo=flutter)
![Security](https://img.shields.io/badge/Security-OWASP_Mobile-red)

> **Proyecto de Simulación Bancaria con Arquitectura Segura (Security by Design).**
> Este repositorio contiene el código fuente de un MVP (Producto Mínimo Viable) diseñado para demostrar prácticas de desarrollo seguro, validación de identidad (simulación RENAPO) y arquitectura de microservicios.

---

## 🏗 Arquitectura del Sistema

El sistema está desacoplado en dos componentes principales siguiendo una arquitectura Cliente-Servidor segura:

1.  **Backend (Core Bancario):** Desarrollado en **Kotlin** con **Spring Boot**. Utiliza **Tomcat Embebido** para un despliegue autocontenido (`.jar`).
2.  **Frontend (Cliente Móvil):** Desarrollado en **Flutter** para generar binarios nativos de Android.
3.  **Base de Datos:** MySQL Relacional (Gestionado vía XAMPP en entorno local).

---

## 🛠 Stack Tecnológico

| Componente | Tecnología | Razón de Selección |
| :--- | :--- | :--- |
| **Backend** | Kotlin + Spring Boot 3 | Null Safety nativo y gestión eficiente de microservicios. |
| **Frontend** | Flutter (Dart) | Desarrollo ágil de UI bancaria y compilación nativa ARM. |
| **Server** | Apache Tomcat 10 (Embedded) | Portabilidad del artefacto y facilidad de escaneo SAST. |
| **Database** | MySQL | Estándar relacional para transacciones ACID. |
| **Seguridad** | Spring Security | Implementación futura de OAuth2/JWT y sanitización de inputs. |

---

## 📋 Requisitos Previos

Para ejecutar este proyecto localmente, necesitas:

* **Java Development Kit (JDK):** Versión 17 o superior.
* **Flutter SDK:** Última versión estable.
* **MySQL Server:** (Recomendado XAMPP para entorno Dev).
* **IDE Sugerido:** IntelliJ IDEA (Backend) y VS Code (Frontend).

---

## ⚙️ Guía de Instalación y Despliegue

Sigue estos pasos para replicar el entorno de desarrollo:

### 1. Configuración de Base de Datos
1.  Inicia el servicio **MySQL** en XAMPP.
2.  Crea una base de datos llamada `banca_db`.
3.  *(Opcional)* Si existe un script `.sql` en la carpeta `/database`, impórtalo.

### 2. Levantar el Backend (Servidor)
Desde la terminal en la carpeta `/backend`:
```bash
# Opción A: Usando Maven Wrapper (Recomendado)
./mvnw spring-boot:run

# Opción B: Ejecutar el JAR generado (Simulación Prod)
java -jar target/banca-core-0.0.1-SNAPSHOT.jar
```

El servidor iniciará en: http://localhost:8080

### 3. Ejecutar la App Móvil
Desde la terminal en la carpeta /frontend:

```Bash
# Instalar dependencias
flutter pub get

# Ejecutar en Emulador Android
flutter run
```
Nota de Red: La aplicación está configurada para apuntar a 10.0.2.2:8080 (alias de localhost en emuladores Android).

## 🔒 Características de Seguridad (Roadmap)

Este proyecto está diseñado para ser auditado por herramientas **SAST** (por ejemplo, Veracode), siguiendo principios de *Security by Design*.

- ✅ **Null Safety:** uso estricto de tipos en Kotlin para reducir errores en tiempo de ejecución.
- 🚧 **Autenticación stateless:** implementación de JWT (en proceso).
- 🚧 **Simulación RENAPO:** servicio interno para validación de identidad.
- 🚧 **Hardening:** sanitización de DTOs para prevenir ataques como SQL Injection.

---

## ☁️ Escalabilidad (Futuro)

Aunque el entorno actual es local (Windows), la arquitectura permite una migración transparente a la nube:

- **Target:** VPS Linux (IONOS).
- **Método:** despliegue del artefacto `.jar` como servicio `systemd`.
- **Red:** configuración de reverse proxy con Nginx y SSL mediante Let's Encrypt.

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

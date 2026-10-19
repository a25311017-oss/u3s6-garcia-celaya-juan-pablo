# 🔐 Aplicación Web con Autenticación y Control de Acceso | Django

Unidad 3 - Semana 6 | **APLICAWEB**

Este proyecto implementa un sistema completo de **Autenticación de Usuarios, Manejo de Sesiones y Control de Acceso Basado en Propietario (Aislamiento de Datos)** utilizando el framework Django y Tailwind CSS.

---

## 📌 Características Principal

* 👤 **Sistema de Autenticación de Fábrica (`django.contrib.auth`):**
  * Registro de usuarios (`UserCreationForm`) con inicio de sesión automático.
  * Inicio de sesión seguro (`AuthenticationForm`).
  * Cierre de sesión seguro mediante peticiones POST.
  * Hash seguro de contraseñas (PBKDF2 por defecto en Django).

* 🛡️ **Protección de Rutas y Seguridad:**
  * Uso del decorador `@login_required` para bloquear accesos no autorizados a la gestión de datos.
  * Configuración de redirección mediante `LOGIN_URL = 'login'`.
  * Protección contra ataques CSRF mediante `{% csrf_token %}`.
  * Checklist pre-deploy de producción (`DEBUG = False`, `ALLOWED_HOSTS`, `CSRF_TRUSTED_ORIGINS`).

* 🔐 **Aislamiento de Datos por Usuario:**
  * Vinculación del modelo `Servicio` con el modelo `User` de Django mediante `ForeignKey`.
  * Asignación automática del autor en el guardado (`servicio.usuario = request.user`).
  * **Acceso Restringido:** Cada usuario solo puede ver, editar y eliminar sus **propios** registros.
  * Validación de propiedad mediante consulta directa (`get_object_or_404(Servicio, pk=pk, usuario=request.user)`).

* 💬 **Feedback de Usuario:**
  * Implementación de mensajes flash (`django.contrib.messages`) con soporte de estilos Tailwind CSS (éxito, error, advertencia).

---

## 🛠️ Tecnologías Utilizadas

* **Lenguaje:** Python 3.x
* **Framework Web:** Django 5.x
* **Base de Datos:** MySQL / PostgreSQL
* **Frontend:** HTML5, Tailwind CSS
* **Despliegue:** Render

---

## 🚀 Instalación y Configuración Local

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/TU-USUARIO/u3s6-apellidopaterno-apellidomaterno-nombres.git](https://github.com/TU-USUARIO/u3s6-apellidopaterno-apellidomaterno-nombres.git)
   cd u3s6-apellidopaterno-apellidomaterno-nombres
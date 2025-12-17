# WebApplicationSecurity-1  
Demo de **autenticación completa** con Spring Security 6 + Spring Boot 3 + Thymeleaf

## 🚀 ¿Qué aprenderás aquí?
- Login / logout clásico con **Spring Security Core**.  
- Protección de rutas (`/admin`, `/user`) y redirección automática.  
- Integración con **Thymeleaf** + `thymeleaf-extras-springsecurity6` para mostrar/ocultar elementos según rol.  
- Gestión de usuarios en memoria (fácil de cambiar a JDBC/JPA).  
- Hot-reload con **DevTools** (Java 21).

## 📦 Stack
| Tecnología | Versión |
|------------|---------|
| Spring Boot | 3.4.2 |
| Spring Security | 6 |
| Java | 21 |
| Thymeleaf | 3 + SpringSecurity extras |
| Build | Maven |

## ▶️ Arranque rápido
```bash
git clone https://github.com/AliciaJava/WebApplicationSecurity-1.git
cd WebApplicationSecurity-1
mvn spring-boot:run
```
Accede a [http://localhost:8080](http://localhost:8080) y prueba:
- Usuario: `user / 12345` → área **USER**
- Administrador: `admin / 12345` → área **ADMIN**

## 🔐 Seguridad incluida
- **Configuración Java** (sin XML):  
  - `HttpSecurity` → login form, logout, CSRF.  
  - `InMemoryUserDetailsManager` → usuarios y roles en memoria.  
- **Vistas protegidas** con `sec:authorize="hasRole('ROLE_ADMIN')"` (Thymeleaf).

## 📁 Estructura clave
```
src/main/java/com.springboot.app.security
├── SecurityConfig.java          # HttpSecurity + usuarios
├── HomeController.java          # rutas públicas / protegidas
└── SpringBootSecurityApp.java   # @SpringBootApplication
src/main/resources/templates
├── login.html                   # form personalizado
├── home.html                    # zona pública
├── user.html                    # solo USER
└── admin.html                   # solo ADMIN
```

## 🔧 Hot-reload
1. Arranca con `mvn spring-boot:run`.  
2. Edita cualquier `.java` o `.html`.  
3. Refresca el navegador → cambios sin reiniciar.

## ✅ Test de seguridad
```bash
mvn test
```
Valida que los endpoints redirigen correctamente según rol.

## 🚀 Próximos pasos que tengo en mente
- Cambiar el `InMemoryUserDetailsManager` por JDBC/JPA para gestionar usuarios desde BBDD.  
- Añadir un formulario de registro y una opción de recuperación de contraseña.  
- Implementar JWT y pasar a una API REST (ya pensando en el libro 2 de la serie).

## 📚 Docs oficiales
- [Spring Security Reference](https://spring.io/projects/spring-security)  
- [Thymeleaf + Spring Security](https://www.thymeleaf.org/doc/articles/springsecurity.html)

**¿Dudas?** Ábrete un issue o únete a la comunidad en Telegram.  
Si el repo te sirve, **dale una ⭐** y compártelo.

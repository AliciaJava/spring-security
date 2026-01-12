# 🔐 WebApplicationSecurity-1

<!-- Badges profesionales -->
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.2-6DB33F?logo=springboot)
![Spring Security](https://img.shields.io/badge/Spring%20Security-6.x-6DB33F?logo=springsecurity)
![Java](https://img.shields.io/badge/Java-21-FF9800?logo=openjdk)
![Maven](https://img.shields.io/badge/Maven-3.x-C71A36?logo=apachemaven)
![Build](https://github.com/AliciaJava/WebApplicationSecurity-1/workflows/CI/badge.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

**Repositorio estrella** 🌟 para aprender **autenticación y autorización** en aplicaciones Spring Boot modernas.

> 🎯 **Objetivo**: Base sólida y extensible antes de saltar a JPA, JWT, OAuth2 o microservicios.

---

## 📑 Índice rápido
1. [¿Qué aprenderás?](#-qué-aprenderás)
2. [Stack tecnológico](#-stack-tecnológico)
3. [Arranque en 30 segundos](#-arranque-en-30-segundos)
4. [Seguridad implementada](#-seguridad-implementada)
5. [Estructura del proyecto](#-estructura-del-proyecto)
6. [Hot Reload](#-hot-reload)
7. [Tests automáticos](#-tests-automáticos)
8. [📸 Capturas de pantalla](#-capturas-de-pantalla)
9. [🚀 Roadmap](#-roadmap)
10. [Recursos](#-recursos)
11. [Comunidad](#-comunidad)

---

## 🎯 ¿Qué aprenderás?
| Habilidad | Ubicación |
|-----------|-----------|
| Login/logout personalizado | `SecurityConfig.java` |
| Protección por roles (`/user`, `/admin`) | `SecurityConfig.java` |
| Thymeleaf + Spring Security Extras | `templates/*.html` |
| Usuarios en memoria (listo para JPA) | `SecurityConfig.java` |
| Hot Reload con DevTools | `pom.xml` |

---

## 🧱 Stack tecnológico
| Tecnología | Versión | Notas |
|------------|---------|-------|
| Spring Boot | 3.4.2 | Última LTS |
| Spring Security | 6.x | Configuración lambda |
| Java | 21 | LTS |
| Thymeleaf | 3.1 | Extras Spring Security |
| Maven | 3.x | Wrapper incluido |

---

## ⚡ Arranque en 30 segundos
```bash
git clone https://github.com/AliciaJava/WebApplicationSecurity-1.git
cd WebApplicationSecurity-1
./mvnw spring-boot:run
```
🌐 Accede a: [http://localhost:8080](http://localhost:8080)

### Credenciales de prueba
| Rol | Usuario | Contraseña |
|-----|---------|------------|
| USER | user | 12345 |
| ADMIN | admin | 12345 |

---

## 🔐 Seguridad implementada
### Configuración (100% Java - sin XML)
```java
http
  .authorizeHttpRequests(auth -> auth
      .requestMatchers("/", "/login").permitAll()
      .requestMatchers("/user").hasRole("USER")
      .requestMatchers("/admin").hasRole("ADMIN")
      .anyRequest().authenticated())
  .formLogin(form -> form
      .loginPage("/login")
      .defaultSuccessUrl("/", true)
      .permitAll())
  .logout(logout -> logout
      .logoutSuccessUrl("/?logout")
      .permitAll());
```

### Usuarios en memoria
```java
@Bean
public InMemoryUserDetailsManager users() {
    return new InMemoryUserDetailsManager(
        User.withUsername("user").password("{noop}12345").roles("USER").build(),
        User.withUsername("admin").password("{noop}12345").roles("USER","ADMIN").build()
    );
}
```

---

## 📁 Estructura del proyecto
```
src/main/java/com/springboot/app/security
├── SpringBootSecurityApp.java
├── SecurityConfig.java
└── controller/
    └── HomeController.java

src/main/resources
├── templates/
│   ├── login.html
│   ├── home.html
│   ├── user.html
│   └── admin.html
└── application.properties
```

---

## 🔁 Hot Reload
1. Ejecuta con `spring-boot-devtools`
2. Modifica `.java` o `.html`
3. Refresca el navegador → cambios sin reiniciar

---

## ✅ Tests automáticos
```bash
./mvnw test
```
Valida:
* Acceso por rol
* Redirecciones
* Seguridad de endpoints

---

## 📸 Capturas de pantalla
### 1. Formulario de login personalizado

<img width="1310" height="613" alt="FORMULARIO" src="https://github.com/user-attachments/assets/5f8f26b5-e3f7-4f10-b411-3bc21cfdbaec" />

### 2. Credenciales de usuario

<img width="1365" height="726" alt="RUN US CLAVE FORMULARIO" src="https://github.com/user-attachments/assets/ff563fbc-de1c-4c15-add2-77e8c36a9c75" />

### 3. Autenticación incorrecta y luego correcta, nombre usuario USER

<img width="1300" height="605" alt="PRUEBA FORMULARIO USER " src="https://github.com/user-attachments/assets/3791345c-0e87-4c8b-abde-42aedf08e927" />

### 4. Área protegida USER

<img width="1297" height="611" alt="AUTENTICACION CORRECTA" src="https://github.com/user-attachments/assets/12cf6f40-9c9f-4ae9-93f4-61fa32f407e0" />

---

## 🚀 Roadmap
* [ ] Migrar a JPA
* [ ] Registro con BCrypt
* [ ] Recuperación de contraseña
* [ ] API REST con JWT
* [ ] Libro 2: OAuth2 + Keycloak

---

## 📚 Recursos
* [Spring Security Official](https://spring.io/projects/spring-security)
* [Thymeleaf + Spring Security](https://www.thymeleaf.org/doc/articles/springsecurity.html)
* [Spring Boot 3 Migration Guide](https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-3.0-Migration-Guide)

---

## 💬 Comunidad
* ¿Dudas? Abre un [Issue](https://github.com/AliciaJava/WebApplicationSecurity-1/issues)
* Únete:
  * [Telegram – Programadores Principiantes](https://t.me/+link)
  * [Telegram – Quiero aprender Java](https://t.me/+link)

⭐ **¿Te ha servido?** ¡Dale una estrella y comparte!









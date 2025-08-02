# Evaluación: Primeros pasos y fundamentos de NestJS

Este cuestionario está diseñado para evaluar tu comprensión sobre los conceptos y buenas prácticas explicados en las lecciones 1, 2 y 3 de la carpeta `docs`. Las preguntas van desde nivel básico a avanzado, simulando una entrevista técnica.

---

## Preguntas básicas

1. **¿Qué es NestJS y cuáles son sus principales ventajas frente a otros frameworks de Node.js?**

**Respuesta:**  
Nest es un framework para construir aplicaciones backend utilizando Typescript. Utiliza "decoradores". Promueve la arquitectura modular: controladores, servicios y módulos. Está inspirado en Angular.

**Calificación:** 8/10  
**Feedback:**  
Tu respuesta es correcta y cubre los puntos clave: TypeScript, decoradores, modularidad e inspiración en Angular.  
**Mejorable:**  
Podrías mencionar explícitamente ventajas como la inyección de dependencias, el soporte para pruebas, la escalabilidad y la estructura orientada a buenas prácticas empresariales.

---

2. **¿Por qué es recomendable desacoplar el frontend y el backend en un proyecto moderno?**

**Respuesta:**  
Es recomendable desacoplar backend y frontend para mantener el principio de unicidad de tareas.

**Calificación:** 6/10  
**Feedback:**  
La respuesta es válida pero muy superficial.  
**Corrección:**  
Además del principio de unicidad de tareas (Single Responsibility Principle), desacoplar permite:

- Escalar y desplegar cada parte de forma independiente.
- Usar diferentes tecnologías en cada capa.
- Mejorar la mantenibilidad y la colaboración entre equipos.
- Facilitar pruebas y reutilización de servicios.

---

3. **¿Qué comando se utiliza para crear un nuevo proyecto NestJS en una carpeta existente?**

**Respuesta:**  
Siempre que tengamos instalado el CLI de Nest, se utiliza el comando: "nest new ." en donde el "." indica que el proyecto se debe crear en la carpeta desde donde se está ejecutando el comando.

**Calificación:** 10/10  
**Feedback:**  
Respuesta precisa y completa.

---

4. **¿Qué archivos y carpetas principales se generan al inicializar un proyecto NestJS?**

**Respuesta:**  
al iniciar un proyecto de nest se generan inicialmente los archivos: "main.ts": es el punto de entrada de la aplicacion, aqui se arranca y se crea la instancia principal de Nest; "app.service.ts": contiene un ejemplo de logica de negocio simple, está separado del controlador; "app.module.ts": es el modulo raiz de la palicacion, aqui se importan y organizan otros modulos ; "app.controllers.ts": define las rutas HTTP y como responden cada una; "app.controllers.spec.ts": que es un test unitario. Además se crean archivos genericos como el package.json

**Calificación:** 9/10  
**Feedback:**  
Respuesta muy completa.  
**Mejorable:**  
Podrías mencionar la carpeta `test/` y archivos de configuración como `nest-cli.json` si quieres ser aún más exhaustivo.

---

5. **¿Cuál es el propósito del archivo `main.ts` en una aplicación NestJS?**

**Respuesta:**  
El archivo "main.ts" es el punto de entrada de la aplicacion, su proposito principal es generar una instancia de nest y levantar el proyecto en un puerto, que puede indicarse en una variable de entorno o por defecto es el puerto 3000

**Calificación:** 10/10  
**Feedback:**  
Respuesta clara y precisa.

---

\*\*¡Buen trabajo! Cuando quieras, continúa

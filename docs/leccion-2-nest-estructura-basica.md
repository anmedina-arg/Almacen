# Lección 2: Estructura básica de un proyecto NestJS

## ¿Qué genera el CLI de NestJS?

Al ejecutar `nest new .`, el CLI crea la estructura mínima para una aplicación NestJS. Es importante entender el propósito de cada archivo y carpeta:

- **src/main.ts**  
  Punto de entrada de la aplicación. Aquí se crea y arranca la instancia principal de Nest.

- **src/app.module.ts**  
  Módulo raíz de la aplicación. Aquí se importan y organizan otros módulos.

- **src/app.controller.ts**  
  Controlador de ejemplo. Define rutas HTTP y cómo responder a ellas.

- **src/app.service.ts**  
  Servicio de ejemplo. Contiene lógica de negocio simple, separado del controlador.

- **test/**  
  Carpeta para pruebas automáticas.

- **package.json**  
  Define dependencias, scripts y metadatos del proyecto.

- **nest-cli.json**  
  Configuración específica del CLI de NestJS.

---

## Buenas prácticas iniciales

- **Separa la lógica de negocio en servicios, no en controladores.**
- **Organiza el código en módulos:** cada funcionalidad debe tener su propio módulo.
- **Documenta tus endpoints y servicios.**
- **Escribe tests desde el inicio, aunque sean básicos.**
- **No mezcles frontend y backend.**

---

## Siguiente paso sugerido

Antes de avanzar con nuevas funcionalidades, asegúrate de comprender cómo se relacionan los controladores, servicios y módulos.  
Esto te permitirá construir aplicaciones escalables

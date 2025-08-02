# Lección 3: Estructura y explicación de los archivos iniciales de un proyecto NestJS

Esta lección documenta los archivos principales generados al crear un proyecto NestJS y explica brevemente el propósito y funcionamiento de cada uno.

---

## 1. `main.ts`

```typescript
import { NestFactory } from '@nestjs/core';
import { AppModule } from './app.module';

async function bootstrap() {
  const app = await NestFactory.create(AppModule);
  await app.listen(process.env.PORT ?? 3000);
}
bootstrap();
```

**¿Qué hace?**

- Es el **punto de entrada** de la aplicación NestJS.
- Usa `NestFactory` para crear una instancia de la app basada en el módulo raíz (`AppModule`).
- Arranca el servidor HTTP en el puerto definido por la variable de entorno `PORT` o, por defecto, en el 3000.

---

## 2. `app.module.ts`

```typescript
import { Module } from '@nestjs/common';
import { AppController } from './app.controller';
import { AppService } from './app.service';

@Module({
  imports: [],
  controllers: [AppController],
  providers: [AppService],
})
export class AppModule {}
```

**¿Qué hace?**

- Define el **módulo raíz** de la aplicación.
- Un módulo en NestJS organiza el código y agrupa controladores, servicios y otros módulos.
- Aquí se declara que el módulo tiene un controlador (`AppController`) y un proveedor/servicio (`AppService`).

---

## 3. `app.controller.ts`

```typescript
import { Controller, Get } from '@nestjs/common';
import { AppService } from './app.service';

@Controller()
export class AppController {
  constructor(private readonly appService: AppService) {}

  @Get()
  getHello(): string {
    return this.appService.getHello();
  }
}
```

**¿Qué hace?**

- Define un **controlador** que maneja las rutas HTTP entrantes.
- El decorador `@Controller()` indica que esta clase es un controlador.
- El método `getHello()` está decorado con `@Get()`, lo que significa que responde a solicitudes GET en la raíz (`/`).
- Usa el servicio `AppService` para obtener la respuesta.

---

## 4. `app.service.ts`

```typescript
import { Injectable } from '@nestjs/common';

@Injectable()
export class AppService {
  getHello(): string {
    return 'Hello World!';
  }
}
```

**¿Qué hace?**

- Define un **servicio** que contiene lógica de negocio reutilizable.
- El decorador `@Injectable()` indica que esta clase puede ser inyectada en otras clases (como el controlador).
- El método `getHello()` retorna un string simple.

**¿Qué significa `@Injectable()`?**

- Es un decorador de NestJS que marca la clase como **inyectable** (puede ser gestionada por el sistema de inyección de dependencias de Nest).
- Permite que Nest cree instancias y resuelva dependencias automáticamente.

---

## 5. `app.controller.spec.ts`

```typescript
import { Test, TestingModule } from '@nestjs/testing';
import { AppController } from './app.controller';
import { AppService } from './app.service';

describe('AppController', () => {
  let appController: AppController;

  beforeEach(async () => {
    const app: TestingModule = await Test.createTestingModule({
      controllers: [AppController],
      providers: [AppService],
    }).compile();

    appController = app.get<AppController>(AppController);
  });

  describe('root', () => {
    it('should return "Hello World!"', () => {
      expect(appController.getHello()).toBe('Hello World!');
    });
  });
});
```

**¿Qué hace?**

- Es un **test unitario** para el controlador.
- Usa el sistema de testing de NestJS para crear un módulo de prueba con el controlador y el servicio.
- Verifica que el método `getHello()` del controlador retorne `"Hello World!"`.

---

## Resumen de conceptos clave

- **Decoradores (`@Controller`, `@Injectable`, `@Get`)**: Son funciones especiales que añaden metadatos a clases y métodos, permitiendo a NestJS gestionar rutas, inyección de dependencias y más.
- **Controlador**: Recibe y responde a solicitudes HTTP.
- **Servicio**: Contiene lógica de negocio y puede ser reutilizado por otros componentes.
- **Módulo**: Agrupa controladores, servicios y otros módulos para organizar la aplicación.

---

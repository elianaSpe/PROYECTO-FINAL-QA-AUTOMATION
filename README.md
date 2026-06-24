# 🏨 Shady Meadows B&B — Proyecto Final QA · Cohorte I 2026

> **Automatización de pruebas funcionales y no funcionales** sobre la aplicación de reservas Shady Meadows (Restful-Booker Platform).

---

## 👥 Integrantes del Grupo

| Nombre Completo | Email |
|----------------|-------|
| [Carina Giacoletti] | [cgiacoletti@hotmail.com] |
| [Tamara Milman] | [tamaramilman3@gmail.com] |
| [Eliana Speranza] | [speranza.eliana.e@gmail.com] |

---

## 🔗 Links Importantes

| Recurso | Link |
|---------|------|
| 📋 Tablero Trello (Bugs) | [Ver Tablero](https://trello.com/b/GpTtbPud/challenge) |
| 📊 Casos de Prueba (Excel/Sheets) | [Ver Planilla](https://docs.google.com/spreadsheets/d/INSERTAR-LINK-AQUI) |
| 🌐 App bajo prueba | [automationintesting.online](https://automationintesting.online) |
| 📖 API Docs | [Swagger](https://automationintesting.online/api/swagger-ui/) |

---

## 🎯 Objetivo del Proyecto

Diseñar, documentar y automatizar pruebas funcionales y de API sobre **Shady Meadows B&B**, un sistema de reservas real con bugs intencionales, aplicando los conocimientos del curso de Quality Engineering y los estándares **ISTQB CTFL v4.0**.

---

## 🏗️ Estructura del Proyecto

── cypress
│   ├── e2e
│   │   └── myTestRestfulBooker.cy.js
│   │
│   ├── fixtures
│   │   ├── contacto.json
│   │   ├── example.json
│   │   └── reserva.json
│   │
│   ├── screenshots
│   │
│   ├── support
│   │   ├── commands.js
│   │   ├── e2e.js
│   │   └── formsCommands.js
│   │
│   └── videos
│       └── myTestRestfulBooker.cy.js.mp4
│
├── node_modules
│
├── README.md
├── cypress.config.js
├── package-lock.json
└── package.json

---

## 🧪 Cobertura de Pruebas

### Suite 3.1 — Reserva Exitosa (Usuario Invitado)
| ID | Caso | Tipo |
|----|------|------|
| CP-001 | Página principal muestra habitaciones disponibles | ✅ Positivo |
| CP-002 | Seleccionar habitación y abrir formulario de reserva | ✅ Positivo |
| CP-003 | Completar y enviar formulario con datos válidos | ✅ Positivo |
| CP-004 | Mensaje de confirmación contiene datos de la reserva | ✅ Positivo |

### Suite 3.2 — Validaciones del Formulario de Reserva
| ID | Caso | Tipo |
|----|------|------|
| CP-005 | Enviar formulario vacío | ❌ Negativo |
| CP-006 | Formulario con solo el nombre | ❌ Negativo |
| CP-007 | Email con formato inválido | ❌ Negativo |
| CP-008 | Teléfono con < 11 dígitos | 🔲 Borde |
| CP-009 | Teléfono con > 21 dígitos | 🔲 Borde |
| CP-010 | Check-out igual al check-in | 🔲 Borde |

### Suite 3.3 — Formulario de Contacto
| ID | Caso | Tipo |
|----|------|------|
| CP-011 | Envío exitoso con datos válidos | ✅ Positivo |
| CP-012 | Formulario de contacto vacío | ❌ Negativo |
| CP-013 | Asunto con menos de 5 caracteres | 🔲 Borde |
| CP-014 | Mensaje con menos de 20 caracteres | 🔲 Borde |
| CP-015 | Email inválido en formulario de contacto | ❌ Negativo |

### Suite 3.4 — Panel de Administración (BONUS)
| ID | Caso | Tipo |
|----|------|------|
| CP-016 | Login exitoso con credenciales válidas | ✅ Positivo |
| CP-017 | Login con contraseña incorrecta | ❌ Negativo |
| CP-018 | Crear nueva habitación desde el admin | ✅ Positivo |

### Suite 3.5 — API REST Testing (BONUS)
| ID | Caso | Tipo |
|----|------|------|
| CP-019 | GET /api/room retorna lista correcta | ✅ Positivo |
| CP-020 | POST /api/booking crea reserva | ✅ Positivo |
| CP-021 | GET /api/room/99999 retorna 404 | ❌ Negativo |
| CP-022 | Login sin credenciales retorna error | ❌ Negativo |

---

## 🚀 Instalación y Ejecución

### Pre-requisitos
- Node.js >= 16.x
- npm >= 8.x

### Instalar dependencias
```bash
npm install
```

### Abrir Cypress (modo interactivo)
```bash
npm run cy:open
```

### Ejecutar todos los tests (modo headless)
```bash
npm run cy:run
```

### Ejecutar solo el archivo principal
```bash
npm run cy:run:spec
```

### Ejecutar en modo visual (con browser)
```bash
npm run cy:run:headed
```

---

## 🐛 Bugs Encontrados

Los bugs se reportan en el tablero de Trello con el formato estándar. A continuación un resumen:

| ID | Título | Severidad | Prioridad | Estado |
|----|--------|-----------|-----------|--------|
| BUG-001 | Reserva permite check-out = check-in (0 noches) | Alta | Alta | Abierto |
| BUG-002 | Mensaje de error no especifica qué campo falló | Media | Media | Abierto |
| BUG-003 | Habitación sin imagen muestra placeholder roto | Baja | Baja | Abierto |
| BUG-004 | Formulario de contacto acepta email sin TLD | Alta | Alta | Abierto |
| BUG-005 | Panel admin permite precio $0 para habitación | Alta | Alta | Abierto |
| BUG-006 | Nombre de habitación en Room 1 aparece como "Room 103 Changed" | Media | Media | Abierto |
| BUG-007 | Teléfono acepta caracteres no numéricos | Media | Alta | Abierto |
| BUG-008 | Descripción de Room 1 no se muestra en UI | Baja | Baja | Abierto |
| BUG-009 | API retorna campos sin documentar en schema | Baja | Baja | Abierto |
| BUG-010 | Login admin no muestra mensaje de error claro | Media | Media | Abierto |
| BUG-011 | La app se resetea cada 10 min sin aviso al usuario | Alta | Alta | Abierto |
| BUG-012 | Formulario de reserva no valida fechas pasadas via API | Alta | Alta | Abierto |

---

## 🛠️ Tecnologías Utilizadas

- **Cypress 13.x** — Framework de automatización E2E
- **JavaScript (ES6+)** — Lenguaje de programación
- **Node.js** — Runtime
- **JSON Fixtures** — Gestión de datos de prueba
- **Cypress Custom Commands** — Reutilización de código

---

## 📐 Buenas Prácticas Implementadas

- ✅ **DRY** (Don't Repeat Yourself) — Custom commands para acciones repetitivas
- ✅ **Fixtures** — Datos de prueba separados del código
- ✅ **Tests independientes** — Cada test tiene su propio `beforeEach`
- ✅ **Comentarios explicativos** — Qué se testea y por qué
- ✅ **Casos positivos, negativos y de borde** (ISTQB BVA/EP)
- ✅ **Manejo de excepciones** — Errores de React no afectan los tests
- ✅ **Retries configurados** — Para la app que se reinicia cada 10 minutos
- ✅ **API + UI testing** — Cobertura mixta

---

## 📋 Criterios ISTQB Aplicados

| Técnica | Aplicación |
|---------|-----------|
| **Partición de Equivalencias (EP)** | Datos válidos vs. inválidos en formularios |
| **Análisis de Valores Límite (BVA)** | Longitud de teléfono (11-21 dígitos), fechas |
| **Prueba de Transición de Estado** | Flujo de reserva: inicio → formulario → confirmación |
| **Prueba de Tabla de Decisión** | Login: credenciales válidas/inválidas/vacías |
| **Prueba de Casos de Uso** | Flujo completo de reserva como usuario invitado |

---

*Cohorte I — 2026 | Quality Engineering*


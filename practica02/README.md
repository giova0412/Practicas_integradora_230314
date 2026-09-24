# Práctica 02: Boceto de Arquitectura de Proyecto Integrador con Archify

> **Universidad Tecnológica de Xicotepec de Juárez (UTXJ)**  
> Carrera: Desarrollo de Software · Cuatrimestre: 230314

---

## 📋 Descripción

Esta práctica consiste en el modelado y documentación de la **arquitectura de una plataforma móvil**, representando los componentes, fronteras de seguridad y flujos de comunicación del sistema. Para ello, se utilizaron herramientas CLI para generar diagramas de arquitectura como código.

---

## 🛠️ Instalación de Herramientas

Para replicar esta práctica, es necesario descargar y configurar **Codex** y **Archify**. A continuación se describen los pasos para instalarlos desde la terminal mediante **npm** (Node Package Manager).

### 1. Instalación de Codex (Codex-CLI)

Codex permite definir la arquitectura de software como código. Para instalarlo de forma global, ejecuta el siguiente comando en tu terminal:

```bash
npm install -g @codex-cli/codex
```
*(Nota: Asegúrate de tener Node.js instalado en tu sistema).*

### 2. Instalación de Archify

Archify es la herramienta encargada de renderizar los modelos generados por Codex en diagramas visuales interactivos (HTML). Para instalarlo, ejecuta:

```bash
npm install -g @archify/cli
```

Una vez finalizadas ambas instalaciones, puedes verificar que se hayan instalado correctamente ejecutando:
```bash
codex --version
archify --version
```

---

## 🏗️ Arquitectura modelada

### Mobile Platform Architecture

El diagrama modela una plataforma móvil completa con los siguientes componentes:

| Componente | Tipo | Descripción |
|---|---|---|
| **Flutter Mobile App** | Frontend | Cliente iOS + Android |
| **Keycloak** | Seguridad | Identidad y tokens de acceso (OAuth 2.0 / OIDC) |
| **FastAPI REST API** | Backend | Endpoints de la aplicación |
| **PostgreSQL** | Base de datos | Datos relacionales |
| **MongoDB** | Base de datos | Datos de documentos |
| **Leaflet / Maps Service** | Externo | Tiles de mapas e interfaz geoespacial |
| **Docker + Docker Compose** | Infraestructura local | Contenedores y orquestación |
| **Git + GitHub** | Control de versiones | Repositorio local y remoto |

### Vistas guiadas del diagrama

1. **Mobile request path** — Flujo de tráfico autenticado desde el cliente móvil hasta los datos persistentes.
2. **Maps integration** — Integración del cliente móvil con el servicio externo de mapas.
3. **Local development** — Flujo de trabajo con Docker Compose, Git y GitHub.

---

## 📸 Capturas del diagrama

A continuación, se muestran algunas vistas del diagrama generado:

### Tema Oscuro — 1440 × 900
![Arquitectura Mobile Platform — modo oscuro 1440x900](../images/mobile-platform-architecture.visual-check.1440x900.dark.png)

### Tema Claro — 1440 × 900
![Arquitectura Mobile Platform — modo claro 1440x900](../images/mobile-platform-architecture.visual-check.1440x900.light.png)

---

## 📁 Archivos de la Práctica

Dentro de esta carpeta (`practica02`), encontrarás los siguientes archivos generados:

- `mobile-platform-architecture.json`: Fuente de datos del diagrama (generado por Codex).
- `mobile-platform-architecture.html`: Diagrama interactivo autocontenido renderizado por Archify.
- `mobile-platform-architecture.visual-check.json`: Metadatos de la verificación visual automatizada.
- `mobile-platform-architecture.visual-check.html`: Reporte de evidencia visual automatizada.

---

## 🔒 Fronteras de seguridad

El diagrama identifica dos fronteras de seguridad principales:

- **Mobile device trust boundary** — Las credenciales y tokens solo cruzan el límite del dispositivo móvil a través de OIDC.
- **Authenticated application boundary** — El acceso a la API está autenticado antes de llegar a los servicios de datos.

---

## 👤 Autor

**Giovanni** · UTXJ · Desarrollo de Software · 230314  
Repositorio: [https://github.com/giova0412/Practicas_integradora_230314](https://github.com/giova0412/Practicas_integradora_230314)

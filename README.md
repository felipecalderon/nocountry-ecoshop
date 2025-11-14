## 💻 EcoShop: Plataforma E-commerce Sostenible

> **EcoShop** es una plataforma de comercio electrónico diseñada para marcas sostenibles. Va más allá de la venta al integrar la **medición, visualización y comunicación del impacto ambiental** de cada producto y compra. Nuestro objetivo es fortalecer la confianza del consumidor y promover decisiones de compra responsables a través de la transparencia y la educación.

### 🎯 Objetivo del Proyecto

Desarrollar una plataforma web de comercio electrónico que:

- ✅ Integre **indicadores de impacto ambiental** (huella de carbono, materiales, origen) por producto.
- ✅ Fomente la **trazabilidad** y la **transparencia**.
- ✅ Ofrezca una **experiencia de usuario fluida, moderna y educativa**, centrada en el consumo positivo.

---

## 🛠️ Arquitectura del Proyecto

El proyecto está dividido en dos componentes principales, gestionados como **submódulos de Git** para mantener una separación limpia entre el _frontend_ y el _backend_.

| Componente         | Tecnología Principal | Descripción                                                                                                                                 | Ubicación (Submódulo) |
| :----------------- | :------------------- | :------------------------------------------------------------------------------------------------------------------------------------------ | :-------------------- |
| **Backend (API)**  | **NestJS (Node.js)** | Servidor API RESTful para la lógica de negocio, autenticación, gestión de inventario, cálculo de impacto ambiental y persistencia de datos. | `back/`               |
| **Frontend (Web)** | **React**            | Interfaz de usuario, incluyendo el catálogo de productos, carrito de compras, checkout, y panel de administración para marcas.              | `front/`              |

---

## ⚙️ Configuración y Ejecución Local

Sigue estos pasos para obtener una copia local del proyecto en funcionamiento.

### 1\. Prerrequisitos

Asegúrate de tener instalado el siguiente software:

- **Git**
- **Node.js** (versión recomendada: 20.x o superior)
- **npm** o **pnpm** (para la gestión de paquetes)

### 2\. Clonación del Repositorio y Submódulos

Clona el repositorio principal e inicializa y actualiza los submódulos:

```bash
# 1. Clonar el repositorio principal
git clone https://github.com/felipecalderon/nocountry-ecoshop.git ecoshop
cd ecoshop

# 2. Inicializar y actualizar los submódulos
git submodule update --init --recursive
```

### 3\. Configuración del Backend (NestJS)

Dirígete a la carpeta del servidor y configura las variables de entorno:

```bash
cd back/

# 1. Instalar dependencias
npm install
# o yarn install

# 2. Configuración de Variables de Entorno
# Crea un archivo .env en back/ a partir de una plantilla .env.example
cp .env.example .env

# Rellena las variables de .env (ej. DB_HOST, JWT_SECRET, PORT, etc.)

# 3. Levantar la aplicación
npm run start:dev
# La API estará disponible en http://localhost:3001
```

### 4\. Configuración del Frontend (React)

En una nueva terminal, dirígete a la carpeta del cliente:

```bash
cd ../front/

# 1. Instalar dependencias
npm install
# o pnpm install

# 2. Levantar la aplicación
npm run start
# La aplicación se abrirá en tu navegador (http://localhost:3000)
```

---

## ✨ Características Principales

### Funcionalidades Específicas

- **Catálogo Detallado:** Fichas de producto con datos ambientales (materiales, origen, emisiones de $\text{CO}_2$).
- **Impacto en Tiempo Real:** Carrito y _checkout_ con cálculo estimado de la **huella de carbono por pedido**.
- **Panel de Administración:** Para marcas, permite la carga de productos, gestión de inventario y visualización de métricas sostenibles.
- **Módulo de Certificaciones:** Visualización de sellos de sostenibilidad (Fair Trade, Carbon Neutral, etc.).
- **Pasarelas de Pago:** Integración segura con proveedores como MercadoPago, Stripe, o PayPal.

### Indicadores Ambientales Clave

| Indicador            | Descripción                                                 | Visualización                                                              |
| :------------------- | :---------------------------------------------------------- | :------------------------------------------------------------------------- |
| **Huella Ecológica** | Cálculo estimado del impacto ambiental por producto/pedido. | Reportes visuales y métricas (`ej.: "evitaste 2 kg de CO₂"`)               |
| **Eco-Badges**       | Sistema de niveles de sostenibilidad.                       | Etiquetas en producto (`🌱 Bajo impacto`, `🌿 Medio impacto`, `🌳 Neutro`) |

### Experiencia de Usuario y No Funcionales

- **Navegación Intuitiva:** Diseño minimalista y claro, enfocado en el impacto positivo.
- **Filtros Inteligentes:** Búsqueda por materiales, origen o tipo de impacto.
- **Sostenibilidad Digital:** Tiempos de carga rápidos, accesibilidad (WCAG) y optimización de recursos (imágenes comprimidas, _dark mode_ opcional).

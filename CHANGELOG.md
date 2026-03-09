# Changelog

Todos los cambios notables en este proyecto serán documentados en este archivo.

El formato está basado en [Keep a Changelog](https://keepachangelog.com/es-ES/1.0.0/),
y este proyecto adhiere al [Versionado Semántico](https://semver.org/lang/es/).

---

## [1.0.0] - 2026-02-11

### 🎉 Primera versión de producción

Primera versión estable de PedidosApp1 con todos los módulos funcionales implementados.

### ✨ Agregado

#### Módulos de Gestión
- Módulo de gestión de artículos con soporte para imágenes
  - CRUD completo (Crear, Leer, Actualizar, Eliminar)
  - Carga de imágenes de productos
  - Búsqueda por código y nombre
  - Asociación con categorías y presentaciones
- Módulo de gestión de categorías
  - CRUD completo de categorías
  - Validación de nombres únicos
- Módulo de gestión de clientes
  - Registro completo de datos del cliente
  - Búsqueda por apellido y número de documento
  - Validación de campos obligatorios
- Módulo de gestión de proveedores
  - Registro de proveedores con datos fiscales
  - Búsqueda por razón social y número de documento
- Módulo de gestión de trabajadores
  - Creación de usuarios con roles (Administrador/Vendedor)
  - Sistema de permisos por rol
- Módulo de presentaciones de artículos
  - Gestión de unidades de medida (unidad, caja, paquete, etc.)

#### Módulos Transaccionales
- Módulo de ingresos al almacén
  - Registro de compras a proveedores
  - Control de stock por lote
  - Registro de fechas de producción y vencimiento
  - Cálculo automático de totales con IGV
  - Generación de detalle de ingreso
- Módulo de ventas
  - Proceso completo de venta a clientes
  - Selección de artículos con validación de stock
  - Cálculo automático de subtotales y totales
  - Aplicación de descuentos
  - Generación de comprobantes de venta
  - Actualización automática de inventario

#### Dashboard y Reportes
- Dashboard analítico con métricas en tiempo real
  - Total de órdenes del período
  - Ingresos totales
  - Número de productos registrados
  - Contador de clientes activos
  - Gráfico de ingresos diarios
  - Gráfico de productos más vendidos
  - Lista de productos con stock bajo (understock)
  - Filtrado de métricas por rango de fechas

#### Sistema de Autenticación
- Login con validación de usuario y contraseña
  - Autenticación contra base de datos SQL Server
  - Validación de roles (Administrador/Vendedor)
  - Manejo de sesión de usuario

#### Interfaz de Usuario
- Navegación principal con menú lateral
  - Iconografía con FontAwesome
  - Navegación intuitiva entre módulos
  - Indicador visual del módulo activo
- Tooltips informativos en campos importantes
- Mensajes de confirmación antes de eliminar registros
- ErrorProvider para validación visual de campos

### 🏗️ Arquitectura y Tecnología

#### Arquitectura en 3 Capas
- **Capa de Presentación:** Windows Forms (10 formularios principales)
- **Capa de Negocio:** Clases de lógica de negocio (CapaNegocio)
- **Capa de Datos:** Acceso a datos con ADO.NET y SQL Server

#### Patrones de Diseño
- Patrón Singleton implementado en formularios principales
  - FrmArticulo, FrmVenta, FrmIngreso
  - Previene múltiples instancias de ventanas
- Separación de responsabilidades entre capas
- Uso de DataGridView para visualización de datos

#### Tecnologías Utilizadas
- Windows Forms con C# .NET Framework 4.8
- SQL Server para persistencia de datos
- FontAwesome.Sharp para iconografía
- ADO.NET para acceso a datos
- Visual Studio 2022 como IDE de desarrollo

### 📊 Estadísticas del Proyecto

- **10 formularios principales** completamente funcionales
- **9 clases de negocio** (NArticulo, NVenta, NIngreso, etc.)
- **8 tablas principales** en base de datos
- **Aproximadamente 3,500 líneas de código** C#

### 🔧 Configuración

#### Base de Datos
- Esquema de base de datos relacional implementado
- Tablas: articulo, categoria, cliente, proveedor, trabajador, venta, detalle_venta, ingreso, detalle_ingreso, presentacion
- Relaciones de integridad referencial
- Procedimientos almacenados para operaciones CRUD

#### Conexión
- Connection string configurable en `app.config`
- Soporte para autenticación SQL Server
- Manejo de excepciones en operaciones de base de datos

### 📝 Documentación

- README.md con instrucciones de instalación
- Comentarios en código para funciones críticas
- Estructura de proyecto organizada y legible

### 🎯 Características Destacadas

- ✅ Interfaz gráfica moderna y profesional
- ✅ Búsqueda y filtrado en tiempo real
- ✅ Validación de datos de entrada
- ✅ Confirmaciones antes de operaciones destructivas
- ✅ Tooltips informativos
- ✅ DataGridView configurados con selección completa de fila
- ✅ Iconos FontAwesome en navegación y botones
- ✅ Sistema de roles para control de acceso

### 🔒 Seguridad

- Autenticación de usuarios requerida
- Control de acceso basado en roles
- Validación de campos obligatorios
- Prevención de eliminaciones accidentales mediante confirmaciones

---

## [Unreleased] - Próximas Versiones

### 🚀 Planeado para v1.1.0

#### Nuevas Características
- [ ] Módulo de reportes avanzados en PDF
- [ ] Exportación de datos a Excel
- [ ] Gráficos adicionales en Dashboard
- [ ] Sistema de backup automático de base de datos
- [ ] Notificaciones de productos próximos a vencer
- [ ] Historial de cambios de precios

#### Mejoras
- [ ] Optimización de consultas SQL
- [ ] Mejora en velocidad de carga de Dashboard
- [ ] Interfaz responsive para diferentes resoluciones
- [ ] Temas claros y oscuros

### 🐛 Correcciones Planeadas para v1.0.1

- [ ] Validación de stock para prevenir valores negativos
- [ ] Corrección de botón "Imprimir" en módulo de categorías
- [ ] Búsqueda de clientes case-insensitive
- [ ] Habilitación de campos en módulo de ingresos
- [ ] Recálculo de totales al eliminar artículos del detalle
- [ ] Validación de fechas de vencimiento en ventas
- [ ] Limpieza de formulario al cancelar operaciones

---

## Tipos de Cambios

- **Agregado** para nuevas características
- **Cambiado** para cambios en funcionalidades existentes
- **Obsoleto** para características que serán eliminadas
- **Eliminado** para características eliminadas
- **Corregido** para corrección de bugs
- **Seguridad** para vulnerabilidades corregidas

---

## Versionado

Este proyecto sigue [Versionado Semántico](https://semver.org/lang/es/):

- **MAJOR** (X.0.0): Cambios incompatibles con versiones anteriores
- **MINOR** (1.X.0): Nuevas funcionalidades compatibles con versiones anteriores
- **PATCH** (1.0.X): Correcciones de bugs compatibles

---

## Enlaces

- [Repositorio en GitHub](https://github.com/brandonsaucedof/PedidosApp1)
- [Reportar un Bug](https://github.com/brandonsaucedof/PedidosApp1/issues/new?labels=bug)
- [Solicitar Feature](https://github.com/brandonsaucedof/PedidosApp1/issues/new?labels=enhancement)
- [Guía de Contribución](CONTRIBUTING.md)

---

<div align="center">

**Mantenido por Brandon Saucedo - Universidad Domingo Savio (UPDS)**

Última actualización: 11 de febrero de 2026

</div>

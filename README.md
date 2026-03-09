# 🛒 PedidosApp1

**Sistema de Gestión de Pedidos para Pequeñas y Medianas Empresas**

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![Platform](https://img.shields.io/badge/platform-Windows-lightgrey.svg)
![Framework](https://img.shields.io/badge/.NET%20Framework-4.8-purple.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

---

## 📋 Descripción

PedidosApp1 es una aplicación de escritorio desarrollada en **Windows Forms con C#** que permite gestionar el ciclo completo de compra-venta para negocios minoristas. El sistema incluye control de inventario, gestión de ventas, registro de ingresos al almacén, y un dashboard analítico con gráficos en tiempo real.

---

## ✨ Características Principales

### 📦 Gestión de Inventario
- ✅ CRUD completo de artículos con soporte para imágenes
- ✅ Organización por categorías
- ✅ Control de presentaciones (unidad, caja, paquete, etc.)
- ✅ Alertas de stock bajo
- ✅ Registro de fechas de vencimiento

### 💼 Gestión Comercial
- ✅ Registro de clientes con datos completos
- ✅ Gestión de proveedores
- ✅ Proceso de ventas con generación de comprobantes
- ✅ Ingresos al almacén con control de lotes
- ✅ Búsqueda y filtrado avanzado

### 📊 Dashboard Analítico
- ✅ Métricas de ventas e ingresos
- ✅ Gráficos de productos más vendidos
- ✅ Análisis de ingresos por período
- ✅ Lista de productos con stock crítico

### 👥 Administración
- ✅ Sistema de autenticación de usuarios
- ✅ Roles: Administrador y Vendedor
- ✅ Gestión de trabajadores

---

## 🛠️ Tecnologías Utilizadas

| Componente | Tecnología |
|------------|------------|
| **Frontend** | Windows Forms C# |
| **Backend** | .NET Framework 4.8 |
| **Base de Datos** | SQL Server |
| **Arquitectura** | 3 Capas (Presentación, Negocio, Datos) |
| **Iconografía** | FontAwesome.Sharp |
| **Patrones** | Singleton, Repository |

---

## 📁 Estructura del Proyecto
```
PedidosApp1/
│
├── CapaNegocio/              # Lógica de negocio
│   ├── NArticulo.cs
│   ├── NVenta.cs
│   ├── NIngreso.cs
│   └── ...
│
├── CapaDatos/                # Acceso a datos (ADO.NET)
│   └── Conexion.cs
│
├── PedidosApp1/              # Capa de presentación
│   ├── FrmPrincipal.cs       # Formulario principal
│   ├── FrmVenta.cs           # Módulo de ventas
│   ├── FrmIngreso.cs         # Módulo de ingresos
│   ├── FrmArticulo.cs        # Gestión de artículos
│   ├── Dashboard.cs          # Dashboard analítico
│   └── ...
│
└── PedidosApp1.sln           # Solución de Visual Studio
```

---

## 🚀 Instalación y Configuración

### Requisitos Previos

- **Sistema Operativo:** Windows 10/11
- **Visual Studio:** 2019 o superior
- **.NET Framework:** 4.8
- **SQL Server:** 2016 o superior

### Pasos de Instalación

#### 1️⃣ Clonar el Repositorio
```bash
git clone https://github.com/brandonsaucedof/PedidosApp1.git
cd PedidosApp1
```

#### 2️⃣ Configurar Base de Datos

1. Abrir SQL Server Management Studio
2. Ejecutar el script de creación de BD: `database/create_database.sql`
3. Ejecutar el script de datos iniciales: `database/seed_data.sql`

#### 3️⃣ Configurar Connection String

Editar el archivo `app.config` en el proyecto `PedidosApp1`:
```xml
<connectionStrings>
  <add name="PedidosDB" 
       connectionString="Server=localhost;Database=PedidosApp;User Id=sa;Password=TuPassword;" 
       providerName="System.Data.SqlClient" />
</connectionStrings>
```

#### 4️⃣ Restaurar Paquetes NuGet

En Visual Studio:
1. Clic derecho en la solución → **Restore NuGet Packages**
2. Esperar a que se descargue `FontAwesome.Sharp` y otras dependencias

#### 5️⃣ Compilar y Ejecutar
```bash
# Opción 1: Desde Visual Studio
Presionar F5 o clic en "Start"

# Opción 2: Desde línea de comandos
msbuild PedidosApp1.sln /p:Configuration=Release
.\PedidosApp1\bin\Release\PedidosApp1.exe
```

---

## 👤 Credenciales de Acceso por Defecto

| Usuario | Contraseña | Rol |
|---------|------------|-----|
| admin | admin123 | Administrador |
| vendedor | vendedor123 | Vendedor |

> ⚠️ **Importante:** Cambiar las contraseñas después del primer inicio de sesión.

---

## 📸 Capturas de Pantalla

### Dashboard Principal
![Dashboard](docs/screenshots/dashboard.png)

### Módulo de Ventas
![Ventas](docs/screenshots/ventas.png)

### Gestión de Artículos
![Artículos](docs/screenshots/articulos.png)

---

## 🔄 Versionado

Este proyecto sigue [Versionado Semántico](https://semver.org/lang/es/).

### Formato: `MAJOR.MINOR.PATCH`

- **MAJOR**: Cambios incompatibles con versiones anteriores
- **MINOR**: Nuevas funcionalidades compatibles
- **PATCH**: Correcciones de bugs

### Historial de Versiones

Ver [CHANGELOG.md](CHANGELOG.md) para el historial completo.

| Versión | Fecha | Descripción |
|---------|-------|-------------|
| 1.0.0 | 2026-02-11 | Primera versión estable |

---

## 🐛 Problemas Conocidos

- [ ] Validación de stock permite valores negativos en algunos casos
- [ ] Botón de imprimir en módulo de categorías no funciona
- [ ] Búsqueda de clientes es case-sensitive

Ver [Issues](https://github.com/brandonsaucedof/PedidosApp1/issues) para más detalles.

---

## 🤝 Contribución

Las contribuciones son bienvenidas. Por favor:

1. Fork el proyecto
2. Crear una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'feat: Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abrir un Pull Request

### Convención de Commits

Seguimos [Conventional Commits](https://www.conventionalcommits.org/):

- `feat:` Nueva funcionalidad
- `fix:` Corrección de bug
- `docs:` Cambios en documentación
- `style:` Formateo, puntos y comas faltantes, etc.
- `refactor:` Refactorización de código
- `test:` Agregar o actualizar tests
- `chore:` Cambios en el build, herramientas, etc.

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver [LICENSE](LICENSE) para más información.

---

## 👨‍💻 Autor

**Brandon Saucedo**
- GitHub: [@brandonsaucedof](https://github.com/brandonsaucedof)
- Universidad: Universidad Domingo Savio (UPDS)
- Carrera: Ingeniería de Software

---

## 🙏 Agradecimientos

- Universidad Domingo Savio (UPDS) por el apoyo académico
- Comunidad de desarrolladores C# y .NET
- Biblioteca FontAwesome por los iconos

---

## 📞 Soporte

¿Problemas o preguntas? 

- 📧 Email: brandon.saucedo@upds.edu.bo
- 🐛 Issues: [GitHub Issues](https://github.com/brandonsaucedof/PedidosApp1/issues)
- 📚 Documentación: [Wiki](https://github.com/brandonsaucedof/PedidosApp1/wiki)

---

<div align="center">

**Hecho con ❤️ para la gestión eficiente de pequeños negocios**

⭐ Si este proyecto te fue útil, considera darle una estrella en GitHub

</div>

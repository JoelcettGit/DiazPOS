# 🎯 DiazPOS - Sistema de Punto de Venta Profesional v1.0.2

![version](https://img.shields.io/badge/version-1.0.2-blue)
![license](https://img.shields.io/badge/license-MIT-green)
![python](https://img.shields.io/badge/python-3.8+-blue)
![platform](https://img.shields.io/badge/platform-Windows%207%2B-lightgrey)

> **DiazPOS** es un sistema de punto de venta (POS) completo y profesional diseñado para **Diaz Distribuidora**, con integración fiscal AFIP, gestión de inventario y reportes avanzados.

---

## ✨ Características Principales

### 🛒 Módulo de Ventas
- Interfaz POS intuitiva y rápida
- Carrito de compras con edición en tiempo real
- Múltiples métodos de pago (Efectivo, Tarjeta, Cheque, Transferencia)
- Generación automática de facturas fiscales
- Impresión térmica (ESC/POS compatible)
- QR code en facturas
- Descuentos por producto o total

### 👥 Módulo de Clientes
- Gestión completa de clientes
- Historial de compras
- Tracking de deudas y pagos
- Límites de crédito configurables
- Contacto y seguimiento

### 📦 Módulo de Inventario
- Control de stock en tiempo real
- Alertas de bajo stock
- Ajustes manuales
- Categorías de productos
- Precios múltiples

### 📊 Reportes & Analytics
- Reportes de ventas (diario, semanal, mensual)
- Análisis de clientes deudores
- Exportación a Excel/PDF
- Gráficos de tendencias
- Dashboard con KPIs

### 🔐 Integración AFIP
- Generación de facturas fiscales automáticas
- Comunicación directa con webservices AFIP
- Numeración secuencial validada
- Validación de CUIT/CUIL
- Soporte para tipos de IVA variables

### 🔄 Sistema de Actualización v2.0
- Actualizaciones automáticas seguras
- Reintentos automáticos (3x)
- Validación de archivos descargados
- Logging completo
- Barra de progreso visual

### 👤 Autenticación & Control de Acceso
- Sistema de usuarios con roles (Admin, Vendedor, Cobranza, Consulta)
- Control de acceso por módulo
- Auditoría de cambios
- Sessiones persistentes

---

## 🚀 Instalación Rápida

### Opción 1: Instalador Automático (Recomendado)

```bash
1. Descargar: DiazPOS_Setup_v1.0.2.exe
2. Ejecutar el instalador
3. Seguir el asistente
4. ¡Listo! Acceso directo en Escritorio
```

## 📋 Requisitos del Sistema

### Mínimo
- **OS:** Windows 7 SP1 o superior
- **RAM:** 1 GB
- **Disco:** 500 MB
- **Pantalla:** 1024x768

### Recomendado
- **OS:** Windows 10/11
- **RAM:** 4-8 GB
- **Disco:** 2 GB
- **Pantalla:** 1920x1080 Full HD
- **Impresora:** Térmica ESC/POS compatible

---

## 📦 Estructura del Proyecto

```
DiazPOS/
├── src/                          # Código fuente
│   ├── ui/                       # Módulos de interfaz (tkinter)
│   │   ├── manager.py           # Ventana principal
│   │   ├── login.py             # Autenticación
│   │   ├── ventas.py            # Interfaz de ventas
│   │   ├── clientes.py          # Gestión de clientes
│   │   ├── dashboard.py         # Reportes y KPIs
│   │   └── container.py         # Contenedor de frames
│   │
│   ├── modules/                  # Lógica de negocio
│   │   ├── utils_ventas.py      # Operaciones de ventas (MVC)
│   │   ├── utils_clientes.py    # Gestión de clientes
│   │   ├── utils_config.py      # Configuración
│   │   ├── afip_connector.py    # Integración AFIP
│   │   └── reportes.py          # Generación de reportes
│   │
│   ├── index.py                  # Punto de entrada (main)
│   └── updater_v2.py             # Sistema de actualización v2
│
├── config/                      # Archivos de configuración
│   ├── config_afip.py           # Configuración afip (cert, key, token)
│   └── config.py                # Constantes y variables globales
│
├── imagenes/                    # Recursos (imágenes, templates)
│   ├── icono/
│   ├   ├── icono_dashboard.ico            # Iconos de aplicación
│   ├   └── ...
│   └── icono_principal
│
├── docs/                         # Documentación
│   ├── usuario/                 # Manuales para usuarios finales
│   │   ├── MANUAL.md            # Manual completo (800+ líneas)
│   │   └── GUIA_RAPIDA.md       # Guía rápida
│   │
│   └── desarrollador/           # Documentación técnica
│       ├── ARQUITECTURA.md      # Arquitectura del sistema
│       ├── MODULOS.md           # Referencia de módulos
│       ├── INSTALACION.md       # Setup para desarrolladores
│       └── API.md               # Referencia de funciones
│
├── data/                        # Datos en runtime (creado automático)
│   ├── database.db              # Base de datos SQLite
│   ├── logs/                    # Registros de ejecución
│   └── exports/                 # Reportes exportados
│
├── requirements.txt             # Dependencias Python
├── LICENSE.txt                  # Licencia MIT
├── CHANGELOG.md                 # Historial de cambios
├── README.md                    # Este archivo
└── .gitignore                   # Archivos a ignorar en git
```

## 📚 Documentación

### Para Usuarios Finales
- **[Manual de Usuario](docs/usuario/MANUAL.md)** - Guía completa de uso
- **[Guía Rápida](docs/usuario/GUIA_RAPIDA.md)** - Operaciones básicas
- **[Solución de Problemas](docs/usuario/TROUBLESHOOTING.md)** - FAQ

---

## 🔧 Dependencias Principales

| Librería | Versión | Propósito |
|----------|---------|----------|
| **tkinter** | built-in | GUI framework |
| **sqlite3** | built-in | Base de datos |
| **Pillow** | 10.0.0 | Procesamiento de imágenes |
| **reportlab** | 4.0.7 | Generación de PDF |
| **requests** | 2.31.0 | HTTP client para updates |
| **numpy** | 1.24.3 | Cálculos numéricos |
| **matplotlib** | 3.8.0 | Gráficos y visualización |
| **pandas** | 2.0.3 | Análisis de datos |
| **PyInstaller** | 6.0.0 | Compilar a .exe |

Ver `requirements.txt` para la lista completa.

---

## 🚀 Uso Rápido

### Crear una Venta

```
1. Login con usuario vendedor
2. Módulo → Ventas
3. Seleccionar cliente (opcional)
4. Agregar productos con cantidad
5. Aplicar descuento (opcional)
6. Presionar F6 → Seleccionar método de pago
7. Confirmar → Imprimir ticket
```

### Registrar Pago de Cliente

```
1. Módulo → Clientes
2. Buscar cliente
3. Clic derecho → "Registrar Pago"
4. Ingresar monto y método
5. Guardar
```

### Generar Reporte

```
1. Módulo → Reportes
2. Seleccionar período
3. Hacer clic en [GENERAR]
4. [EXPORTAR] a Excel/PDF
```

---

## 🆘 Solución de Problemas

### "La app no abre"
```bash
# Verificar si Python está instalado
python --version

# Ejecutar en debug mode
python index.py
```

### "Error de actualización"
```bash
# Ver logs detallados
Archivo: %APPDATA%\DiazPOS\logs\updater.log

# O usar herramienta de debug
python scripts\debug_updater.py
```

### "La impresora no imprime"
```bash
# Verificar conexión
Menú → Configuración → Impresora → [PROBAR]

# Reiniciar impresora e intentar nuevamente
```

Ver `docs/usuario/TROUBLESHOOTING.md` para más problemas.

---

## 🔐 Seguridad

- ✅ Passwords con hash SHA256
- ✅ Validación de inputs SQL injection
- ✅ SSL/TLS en todas las comunicaciones
- ✅ Auditoría de cambios
- ✅ Backups automáticos

---

## 📊 Estadísticas del Proyecto

| Métrica | Valor |
|---------|-------|
| **Líneas de Código** | 3000+ |
| **Líneas de Documentación** | 5000+ |
| **Módulos** | 12+ |
| **Funciones** | 150+ |
| **Tests** | 50+ |
| **Cobertura** | 85%+ |

---

## 📈 Roadmap

### v1.1.0 (Enero 2026)
- [ ] Multi-sucursal
- [ ] Compras de stock
- [ ] Devoluciones

### v1.2.0 (Febrero 2026)
- [ ] API REST
- [ ] Sincronización nube
- [ ] Reportes BI avanzados

### v2.0.0 (Q2 2026)
- [ ] Web app (HTML5)
- [ ] App móvil
- [ ] Data warehouse

---

## 📝 Licencia

Este proyecto está licenciado bajo la Licencia MIT - ver archivo [LICENSE.txt](LICENSE.txt)

---

## 👥 Soporte

| Canal | Detalles |
|-------|----------|
| **Email** | joelcett@gmail.com |
| **GitHub Issues** | https://github.com//JoelcettGit |
| **Horarios** | Lunes-Viernes 09:00-18:00 ART |

---

## 🎓 Créditos

**Desarrollado por:** Equipo Técnico Diaz  
**Versión:** 1.0.0
**Última actualización:** 1 de Diciembre de 2025  
**Python:** 3.8+  
**Licencia:** MIT

---

## 📞 Contacto

**Diaz Distribuidora**  
📧 joelcett@gmail.com 
🌐 https://joeldiaz.vercel.app  

---

> **💡 Consejo:** Consultar la documentación completa en la carpeta `docs/` para obtener más información detallada.

**¡Gracias por usar DiazPOS! 🚀**

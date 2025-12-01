# 🎯 ÍNDICE RÁPIDO - DiazPOS v1.0.1

## 📍 Acceso Rápido a Documentación

### Para Usuarios Finales
- 📖 **[Manual de Usuario](docs/usuario/MANUAL.md)** - Guía completa (850+ líneas)
  - Cómo instalar
  - Cómo usar cada módulo
  - Atajos de teclado
  - Troubleshooting

### Información General
- 📖 **[README](README.md)** - Overview del proyecto
- 📝 **[CHANGELOG](CHANGELOG.md)** - Historial de versiones (No tenemos hasta hoy)
- ⚖️ **[LICENSE](LICENSE.txt)** - Licencia MIT
---


## 📊 Estadísticas

| Métrica | Valor |
|---------|-------|
| **Documentación** | 6000+ líneas |
| **Archivos doc** | 10 |
| **Módulos** | 12+ |
| **Funciones** | 50+ |
| **Tamaño doc** | 180 KB |
| **Diagramas** | 15+ |
| **Ejemplos** | 50+ |

---

## 🚀 Pasos Iniciales

### 1️⃣ Instalar
```bash
# Opción A: Con instalador (recomendado)
DiazPOS_Setup_v1.0.1.exe
```

### 2️⃣ Usar
1. Abrir DiazPOS
2. Login: admin / pedirla123456
3. Cambiar contraseña
4. ¡Listo! Consultar MANUAL.md para operaciones

---

## 📍 Ubicaciones Importantes

| Elemento | Ubicación |
|----------|-----------|
| **Datos BD** | `%APPDATA%\DiazPOS\data\database.db` |
| **Logs** | `%APPDATA%\DiazPOS\logs\updater.log` |
| **Documentación** | `c:\diaz_pos\docs\` |

---

### Bases de Datos
```bash
# Conectar a BD
sqlite3 %APPDATA%\DiazPOS\data\database.db

# Ver tablas
.tables

# Ver schema
.schema
```

---

## 🔐 Credenciales por Defecto

| Usuario | Password | Rol |
|---------|----------|-----|
| admin | pedirla | Administrador |

> ⚠️ **IMPORTANTE:** Cambiar en primer login

---

## 📊 Módulos del Sistema

| Módulo | Archivo | Función |
|--------|---------|---------|
| **Ventas** | `ventas.py` | Interface POS |
| **Clientes** | `clientes.py` | Gestión clientes |
| **Inventario** | `inventario.py` | Control stock |
| **Reportes** | `reportes.py` | Análisis datos |
| **Dashboard** | `dashboard.py` | KPIs |
| **Autenticación** | `login.py` | Usuarios |
| **AFIP** | `afip_connector.py` | Fiscalidad |
| **Actualización** | `updater_v2.py` | Auto-update |

---

## 🎯 Características Clave

✅ Interfaz POS profesional  
✅ Generación de facturas PDF + QR  
✅ Impresión térmica (ESC/POS)  
✅ Integración AFIP  
✅ Gestión de clientes y deudas  
✅ Control de inventario  
✅ Reportes y análisis  
✅ Actualización automática segura  
✅ Multiusuario con roles  
✅ Base de datos persistente  

---

## 🔗 Enlaces Importantes

- 📖 [Manual Completo](docs/usuario/MANUAL.md)
- 📝 [Cambios](CHANGELOG.md)

---


### Actualización
```bash
# Sistema automático detecta nuevas versiones
# Si necesita manual:
1. Descargar nuevo DiazPOS.exe
2. Ejecutar update_launcher.bat (se crea automático)
3. Reinicia app con nueva versión
```

---

## 🆘 Ayuda Rápida

### ❓ La app no abre
```bash
# Verificar Python
python --version

# Ejecutar con debug
python index.py

# Ver logs
type %APPDATA%\DiazPOS\logs\updater.log
```

### ❓ Error de actualización
```bash
# Ver detalles
python scripts\debug_updater.py

# Opción 2
type %APPDATA%\DiazPOS\logs\updater.log
```

### ❓ Impresora no funciona
```bash
# Verificar en Configuración
Menú → Configuración → Impresora → [PROBAR]

# Si error, reiniciar impresora
```

---

## 📞 Contacto

- **Email:** joelcett@gmail.com
- **Web:** https://joeldiaz.vercel.app

---

## 📅 Versionado

| Versión | Fecha | Estado |
|---------|-------|--------|
| **1.0.0** | 1/12/2025 | ✅ Actual |

---

## ✅ Validación

- ✅ Código testeado
- ✅ Documentación completa
- ✅ Build automático
- ✅ Instalador profesional
- ✅ Listo para producción

---

**Última actualización:** 1 de Diciembre de 2025  
**Versión:** 1.0.0  
**Licencia:** MIT

🚀 **¡Listo para usar!**

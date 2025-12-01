# 📖 Manual de Usuario - DiazPOS v1.0.1

## 🎯 Índice de Contenidos

1. [Introducción](#introducción)
2. [Instalación](#instalación)
3. [Primeros Pasos](#primeros-pasos)
4. [Módulos Principales](#módulos-principales)
5. [Operaciones Comunes](#operaciones-comunes)
6. [Reportes](#reportes)
7. [Solución de Problemas](#solución-de-problemas)
8. [Atajos de Teclado](#atajos-de-teclado)

---

## 📋 Introducción

**DiazPOS** es un sistema de punto de venta (POS) profesional para **Diaz Distribuidora** que permite:

✅ Registrar ventas y generar facturas fiscales  
✅ Gestionar inventario de productos  
✅ Administrar clientes y deudas  
✅ Generar reportes de ventas  
✅ Integración con AFIP (impuestos)  
✅ Impresión de tickets en impresoras térmicas  

### Requisitos del Sistema

- **Windows 7+** o Windows Server 2012+
- **1 GB RAM mínimo** (2 GB recomendado)
- **500 MB espacio en disco**
- Impresora térmica (ESC/POS compatible) - Opcional
- Conexión a internet para actualización automática

---

## 💾 Instalación

### Instalador Automático (Recomendado)

1. Descargar: `DiazPOS_Setup.exe`
2. Ejecutar el instalador
3. Seleccionar carpeta destino (recomendado: C:\Program Files\DiazPOS\)
4. Seleccionar crear acceso directo en Escritorio
5. Esperar a que finalice
6. Hacer clic en "Terminar"

### Primera Ejecución

```
1. Doble clic en ícono "DiazPOS" del escritorio
2. Esperar 5-10 segundos (primera carga)
3. Pantalla de login
```

---

## 🚀 Primeros Pasos

### Pantalla de Login

```
┌─────────────────────────────────┐
│         DIAZ POS v1.0.1         │
├─────────────────────────────────┤
│                                 │
│  Usuario:  [          ]        │
│  Password: [          ]        │
│                                 │
│  ☑ Recordar usuario            │
│                                 │
│       [ENTRAR]  [SALIR]        │
│                                 │
└─────────────────────────────────┘
```

### Credenciales por Defecto

> ⚠️ **IMPORTANTE:** Cambiar contraseña en primer login

| Usuario | Password | Rol |
|---------|----------|-----|
| admin | pedirla | Administrador |

### Cambiar Contraseña

1. Entrar con usuario actual
2. Ir a: Menú → Configuración → Cambiar Contraseña
3. Ingresar contraseña actual
4. Ingresar nueva contraseña 2 veces
5. Hacer clic en "Guardar"

---

## 🎯 Módulos Principales

### 📊 1. VENTAS (F5 para abrir)

**Función:** Registrar ventas y emitir facturas

#### Paso a Paso - Crear una Venta

**1. Seleccionar Cliente (Opcional)**
```
Si cliente es conocido:
  - Click en "Buscar Cliente"
  - Escribir nombre/DNI
  - Seleccionar de la lista
  
Si es cliente nuevo:
  - Click en "Cliente Nuevo"
  - Ingresar datos
  - Guardar
```

**2. Agregar Productos**
```
  1. En panel "Productos disponibles" (izquierda)
  2. Escribir nombre/código del producto
  3. Doble-click para agregar (cantidad = 1)
  
  O manualmente:
  1. Seleccionar producto
  2. Cambiar cantidad deseada
  3. Hacer clic en "Agregar al Carrito"
```

**3. Carrito de Compra**
```
Productos en carrito          Cantidad    Precio Unit.  Subtotal
─────────────────────────────────────────────────────
Laptop Dell XPS              1           $899.00      $899.00
Mouse Logitech               2           $45.00       $90.00
                                                   ───────────
                                         TOTAL:    $989.00
```

**4. Aplicar Descuento (Opcional)**
```
- Seleccionar tipo descuento:
  ○ Porcentaje (ej: 10%)
  ○ Monto fijo (ej: $100)
- Ingresar valor
- Presionar ENTER
```

**5. Procesar Pago - Presionar F6**
```
Diálogo de Pago:
  
  Método de Pago:  [▼ SELECCIONAR]
                    - Efectivo
                    - Tarjeta Crédito
                    - Tarjeta Débito
                    - Cheque
                    - Transferencia
  
  Monto:          [              ] $989.00
  Cambio:         $ 0.00
  
  [PROCESAR PAGO]  [CANCELAR]
```

**6. Confirmar Venta**
```
✓ Venta procesada correctamente
  - Número de factura: 001-00001234
  - Fecha: 01/12/2025 14:35
  - Total: $989.00
  
  ¿Desea imprimir ticket?
  [SÍ]  [NO]
```

**7. Imprimir Ticket o Guardar PDF**
```
- Automático en impresora térmica
- O guardar PDF en: Descargas/Facturas/
```

#### Atajos de Ventas

| Atajo | Acción |
|-------|--------|
| **F5** | Actualizar lista de productos |
| **F6** | Abrir diálogo de pago |
| **F10** | Finalizar venta actual |
| **DEL** | Remover producto del carrito |
| **+/-** | Aumentar/disminuir cantidad |

### 👥 2. CLIENTES (Menú → Clientes)

**Función:** Gestionar datos de clientes, historial, pagos

#### Agregar Nuevo Cliente

```
Nombre:          [                    ]  (Ej: Juan García)
DNI:             [                    ]  (11 dígitos)
Email:           [                    ]  (juan@email.com)
Teléfono:        [                    ]  (+54 9 11 XXXX)
Dirección:       [                    ]  (Opcional)
Límite Crédito:  $ [              ]    (Ej: $5000)

              [GUARDAR]  [CANCELAR]
```

#### Listar Clientes

```
Todos los Clientes
Buscar: [                      ] 🔍

Nombre          DNI         Teléfono      Deuda
─────────────────────────────────────────────────
Juan García     11222333    +54911XXXX    $450.00
María López     12444555    +54911YYYY    $0.00
Carlos Ruiz     10666777    +54911ZZZZ    $1200.00

Clic derecho → Ver historial/Registrar pago
```

#### Registrar Pago de Cliente

```
1. Buscar cliente en lista
2. Clic derecho → "Registrar Pago"
3. Ingresar datos:

   Monto:        $ [       ]
   Método:       [▼ Efectivo ▼]
   Referencia:   [          ]  (Ej: Cheque #123)
   
   [GUARDAR PAGO]
```

### 📦 3. INVENTARIO (Menú → Inventario)

**Función:** Ver y gestionar stock de productos

```
Productos en Stock

Código   Nombre              Stock    Mínimo    Estado
────────────────────────────────────────────────────
001      Laptop Dell XPS     5        3         ✓ OK
002      Mouse Logitech      1        5         ⚠ BAJO
003      Monitor 24"         0        2         ✗ AGOTADO

Clic derecho → Ajustar stock / Agregar producto
```

#### Agregar Nuevo Producto

```
Código:          [    ]     (Ej: 004)
Nombre:          [                    ]
Descripción:     [                    ]
Precio Costo:    $ [         ]
Precio Venta:    $ [         ]
Stock Actual:    [    ]
Stock Mínimo:    [    ]
Categoría:       [▼ Seleccionar]

              [GUARDAR]  [CANCELAR]
```

### 📈 4. REPORTES (Menú → Reportes)

**Función:** Análisis de ventas, inventario y cliente

#### Reporte de Ventas Diarias

```
Fecha: [01/12/2025]

Total de Ventas:    5 transacciones
Monto Total:        $4,890.00
Ticket Promedio:    $978.00
Método más usado:   Efectivo (60%)
```

#### Reporte de Clientes Deudores

```
Clientes con deuda

Nombre          Deuda Total    Fecha Última Compra
──────────────────────────────────────────────────
Carlos Ruiz     $1,200.00      30/11/2025
Roberto Gómez   $500.00        28/11/2025
Total Deuda:    $1,700.00
```

#### Exportar Reporte

```
Formato:  [▼ PDF]
          - PDF
          - Excel (.xlsx)
          - CSV
          
[EXPORTAR] → Se guarda en: Descargas/Reportes/

Archivo: Reporte_Ventas_01-12-2025.pdf
```

### ⚙️ 5. CONFIGURACIÓN (Menú → Configuración)

**Función:** Ajustar parámetros del sistema

```
CONFIGURACIÓN GENERAL

Empresa:         [Diaz Distribuidora        ]
CUIT/CUIL:       [20123456789               ]
Domicilio:       [Av. Principal 123         ]

IMPRESORA
Tipo:            [▼ Térmica ESC/POS]
Puerto:          [▼ COM3              ]
Verificar:       [PROBAR CONEXIÓN]

AFIP (Fiscal)
Modo:            ☑ Producción  ○ Pruebas
Punto de Venta:  [1  ]

ACTUALIZACIONES
Auto-actualizar: ☑ Habilitado
Revisar cada:    [24] horas
Última:          01/12/2025 14:30

              [GUARDAR]  [CANCELAR]
```

---

## ⚙️ Operaciones Comunes

### Modificar Venta Anterior

1. Ir a: Menú → Historial de Ventas
2. Buscar venta por:
   - Fecha
   - Número de factura
   - Cliente
3. Clic derecho en venta → "Reimpimir Ticket"

### Cambiar Precio de Producto

1. Menú → Inventario
2. Clic derecho en producto → "Editar"
3. Modificar "Precio Venta"
4. Guardar cambios

### Deshabilitar Usuario

1. Menú → Administración → Usuarios
2. Seleccionar usuario
3. Botón "Deshabilitar"
4. Confirmar

### Respaldar Datos

1. Menú → Herramientas → Crear Respaldo
2. Seleccionar ubicación (USB/Google Drive)
3. Esperar a que finalice

---

## 📊 Reportes

### Generar Reporte de Ventas

```
1. Menú → Reportes
2. Seleccionar:
   - Período: [Hoy] [Semana] [Mes] [Personalizado]
   - Si "Personalizado":
     • Desde: [01/12/2025]
     • Hasta: [31/12/2025]
3. Hacer clic en [GENERAR]
4. Ver datos o [EXPORTAR]
```

### Exportar a Excel

```
1. Generar reporte (ver arriba)
2. Botón [EXPORTAR]
3. Seleccionar formato:
   - Excel (.xlsx)
   - PDF
4. Guardar en carpeta elegida
5. Archivo se abre automáticamente
```

---

## 🆘 Solución de Problemas

### "Contraseña incorrecta"

**Síntoma:** No puedo entrar  
**Solución:**

```
1. Verificar mayúsculas/minúsculas
2. Borrar Caps Lock si está activo
3. Probar usuario "admin" contraseña "123456"
4. Si no funciona, contactar administrador
```

### "La impresora no imprime"

**Síntoma:** Aparece error al imprimir  
**Solución:**

```
1. Verificar que impresora esté encendida
2. Verificar conexión (USB/Serial):
   - Menú → Configuración → Impresora → [PROBAR]
3. Si dice "OK", problema en ticket:
   - Intentar imprimir de nuevo
   - Si persiste, contactar soporte
```

### "Error de actualización"

**Síntoma:** La app se cierra sin avisar  
**Solución:**

```
1. Buscar archivo: C:\Users\[Usuario]\AppData\Roaming\DiazPOS\logs\updater.log
2. Abrir con Bloc de Notas
3. Buscar línea con "ERROR"
4. Captura de pantalla + enviar a soporte
```

### "Base de datos corrupta"

**Síntoma:** "Error de BD" al entrar  
**Solución:**

```
1. NO cerrar app bruscamente
2. Menú → Herramientas → Reparar Base de Datos
3. Si no funciona:
   - Hacer respaldo (Menú → Herramientas → Respaldo)
   - Restaurar de respaldo anterior
   - Si no hay respaldo, contactar soporte
```

### Aplicación lenta

**Síntoma:** Demora en abrir menús o reportes  
**Solución:**

```
1. Cerrar otras aplicaciones
2. Reiniciar DiazPOS
3. Limpiar cache:
   - Menú → Herramientas → Limpiar Cache
4. Si persiste:
   - Verificar espacio en disco (mínimo 1 GB)
   - Aumentar RAM del sistema
```

### "No hay conexión a internet"

**Síntoma:** Error al actualizar  
**Solución:**

```
1. Verificar conexión Wi-Fi/Red
2. Hacer ping: Abrir CMD y escribir:
   ping 8.8.8.8
3. Si dice "Request timed out":
   - Reiniciar router
   - Contactar ISP
4. Si tiene conexión:
   - Problema del servidor de actualización
   - Intentar más tarde
```

---

## ⌨️ Atajos de Teclado

### Atajos Globales

| Tecla | Acción |
|-------|--------|
| **F1** | Abrir ayuda |
| **F5** | Refrescar datos actuales |
| **F10** | Finalizar operación actual |
| **ALT+F4** | Cerrar aplicación |

### En Pantalla de Ventas

| Tecla | Acción |
|-------|--------|
| **F6** | Abrir diálogo de pago |
| **F10** | Finalizar venta |
| **DEL** | Eliminar producto del carrito |
| **+** | Aumentar cantidad |
| **-** | Disminuir cantidad |
| **ESC** | Cancelar operación |

### En Listas (Clientes, Productos, etc.)

| Tecla | Acción |
|-------|--------|
| **ENTER** | Seleccionar item |
| **FLECHA UP/DOWN** | Navegar lista |
| **CTRL+F** | Buscar |
| **CTRL+N** | Nuevo item |
| **CTRL+E** | Editar item |
| **SUPR** | Eliminar item |

---

## 📞 Soporte Técnico

### Información de Sistema

Para reportar problemas, proporcionar:

1. **Versión:** Menú → Acerca de
2. **Logs:** C:\Users\[Usuario]\AppData\Roaming\DiazPOS\logs\
3. **Captura de pantalla** del error
4. **Pasos** que reproduzcan el problema

### Contactos

- **Email:** soporte@diazpos.com
- **Teléfono:** +54 11 XXXX-XXXX
- **WhatsApp:** +54 9 11 XXXX-XXXX
- **Horarios:** Lunes a Viernes, 9:00-18:00

---

## 📅 Historial de Cambios

**v1.0.0 (Actual)**
- ✅ Sistema de actualización automática mejorado
- ✅ Corrección de errores en cálculo de ventas
- ✅ Nueva interfaz más intuitiva

**v1.0.0**
- ✅ Lanzamiento inicial
- ✅ Módulos básicos: Ventas, Clientes, Inventario
- ✅ Generación de facturas AFIP

---

**Manual versión:** 1.0.0
**Última actualización:** Diciembre 1, 2025  
**Licencia:** © 2025 Diaz Distribuidora - Todos los derechos reservados

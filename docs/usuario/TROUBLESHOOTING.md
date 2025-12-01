# ⚡ Troubleshooting Rápido - Sistema de Actualización

## 🆘 Problema: "Se cierra y no abre más"

### Solución 1: Ver qué fue lo que pasó
```powershell
# Abre la carpeta de logs
explorer $env:APPDATA\DiazPOS\logs
# Busca updater.log - allí está toda la información
```

### Solución 2: Limpiar archivos problemáticos
```powershell
# Eliminar instaladores que quedaron a mitad de descarga
Remove-Item "$env:APPDATA\DiazPOS\updates\*.exe" -Force
Remove-Item "$env:APPDATA\DiazPOS\updates\*.bat" -Force

# Eliminar logs viejos
Remove-Item "$env:APPDATA\DiazPOS\logs\*.log" -Force
```

### Solución 3: Forzar reinicio
```powershell
# Matar procesos de DiazPOS si quedaron colgados
taskkill /IM DiazPOS.exe /F

# Esperar 2 segundos y reiniciar
Start-Sleep -Seconds 2
& "C:\Program Files\DiazPOS\DiazPOS.exe"  # Ajustar path si es diferente
```

---

## 🔍 Problema: "No descarga la actualización"

### Causa 1: URL de Google Drive inválida/expirada
```powershell
# Probar si la URL funciona
$url = "https://drive.google.com/uc?export=download&id=1EooE4iEa6s-UdbvSeDUFVN2Euo1hbIr9"
Invoke-WebRequest -Uri $url -Method Head

# Si da error, necesitas:
# 1. Volver a compartir el archivo en Drive
# 2. Obtener el nuevo ID
# 3. Actualizar en updater_v2.py
```

### Causa 2: Conexión de internet lenta
- El sistema reintenta 3 veces automáticamente
- Cada intento espera 60 segundos
- Si sigue fallando, revisar conexión de red

### Causa 3: Google Drive bloqueando descarga
Google a veces requiere confirmación de virus scan. Solución:
```python
# En updater_v2.py, agregar parámetro de confirmación:

def download_file_with_progress(url, output_path, retries=MAX_RETRIES):
    # Agregar confirmación de Google Drive
    url_with_confirm = url + "&confirm=t"
    # Usar url_with_confirm en lugar de url
```

---

## ❌ Problema: "El archivo no es un EXE válido"

### Qué significa
Google Drive envió un HTML en lugar del archivo (error page)

### Solución
1. Ir a Google Drive
2. Compartir el archivo correctamente:
   - Click derecho → "Compartir"
   - Cambiar a "Cualquiera con el enlace"
   - Copiar enlace
   - Obtener el ID y actualizar en `updater_v2.py`

3. Alternativa: Usar GitHub Releases (más confiable)

---

## ⏱️ Problema: "Timeout - el servidor tardó demasiado"

### Causa
Conexión lenta o servidor de Google Drive saturado

### Solución
El sistema reintenta automáticamente. Si persiste:

1. Esperar a hora menos congestionada
2. Cambiar a GitHub Releases (servidor más rápido)
3. Usar VPN si está en región con acceso limitado

---

## 🚨 Problema: "La actualización no termina"

### Síntomas
- Se descarga pero no cierra la app
- El batch no ejecuta el instalador
- DiazPOS sigue corriendo

### Debugging
```powershell
# Ver qué procesos están corriendo
Get-Process | Where-Object Name -like "*Diaz*"
Get-Process | Where-Object Name -like "*update*"

# Ver si hay archivos batch esperando
Get-ChildItem "$env:APPDATA\DiazPOS\updates\*.bat"

# Ver contenido del batch que se creó
Get-Content "$env:APPDATA\DiazPOS\updates\update_scheduler.bat"
```

### Solución
```powershell
# Matar procesos pendientes
taskkill /IM DiazPOS.exe /F
taskkill /IM update_scheduler.bat /F

# Limpiar archivos
Remove-Item "$env:APPDATA\DiazPOS\updates\update_scheduler.bat" -Force

# Reiniciar
& "C:\Program Files\DiazPOS\DiazPOS.exe"
```

---

## 📋 Problema: "No puedo ver los logs"

### Abrir logs desde la aplicación
```python
# En la app, una vez se implemente:
# Menú → Ayuda → Ver logs de actualización
```

### Abrir logs manualmente
```powershell
# Abrir archivo de logs
notepad $env:APPDATA\DiazPOS\logs\updater.log

# Ver últimas 50 líneas
Get-Content "$env:APPDATA\DiazPOS\logs\updater.log" -Tail 50

# Buscar errores
Select-String "ERROR" "$env:APPDATA\DiazPOS\logs\updater.log"
```

---

## 🔧 Problema: "Cambié la URL pero sigue usando la vieja"

### Verificar cambios fueron guardados
```powershell
# Ver contenido de updater_v2.py
Select-String "INSTALLER_URL" "c:\diaz_pos\updater_v2.py"
```

### Reiiciar Python
Si estaba corriendo Python:
```powershell
taskkill /IM python.exe /F
```

### Si aún no funciona
```powershell
# Limpiar cache de Python
Remove-Item "c:\diaz_pos\__pycache__" -Recurse -Force
Remove-Item "c:\diaz_pos\*.pyc" -Force
```

---

## 🧪 Testing Rápido

### Script completo de prueba
```powershell
# 1. Abrir debug_updater.py
python c:\diaz_pos\debug_updater.py

# Menú:
# 1 = Ver status
# 2 = Verificar URLs
# 3 = Probar descarga de versión
# 4 = Probar flujo completo
# 5 = Ver logs (GUI)
# 6 = Limpiar instaladores
```

---

## 💡 Tips y Trucos

### Simular actualización sin descargar (testing)
```python
# En updater_v2.py, comentar descarga real:

def download_file_with_progress(url, output_path, retries=MAX_RETRIES):
    # Crear archivo fake para testing
    fake_exe = b'MZ' + b'\x00' * 1024  # Fake EXE con header válido
    with open(output_path, 'wb') as f:
        f.write(fake_exe)
    return True
```

### Ver URL de Google Drive que se está usando
```python
# En updater_v2.py:
logger.info(f"Descargando desde: {INSTALLER_URL}")
```

### Aumentar timeout para conexiones lentas
```python
# En updater_v2.py:
DOWNLOAD_TIMEOUT = 120  # 2 minutos en lugar de 60 segundos
```

---

## ✅ Checklist de Resolución

Si aún no funciona, seguir este orden:

- [ ] Ver archivo de logs (`updater.log`)
- [ ] Verificar que URLs de Google Drive sean compartidas correctamente
- [ ] Limpiar archivos en `updates/` folder
- [ ] Reiniciar DiazPOS
- [ ] Ejecutar `debug_updater.py` opción 2 (verificar URLs)
- [ ] Ejecutar `debug_updater.py` opción 4 (flujo completo)
- [ ] Si persiste, pastebin los logs para investigar
- [ ] Considerar migrar a GitHub Releases

---

## 📞 Reporte de Bug

Si nada funciona, proporcionar:

1. **Archivo de logs:** `%APPDATA%\DiazPOS\logs\updater.log`
2. **Versión actual:** `config.py` - `APP_VERSION`
3. **Versión disponible:** URL de LATEST_VERSION_URL
4. **Sistema operativo:** `ver` en cmd
5. **Conexión:** velocidad de internet (`speedtest.net`)
6. **Antivirus:** qué programa antivirus está usando
7. **Pasos para reproducir:** describir exactamente qué hizo

---

**Última actualización:** 1 de Diciembre, 2025

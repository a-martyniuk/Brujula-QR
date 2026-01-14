# QR Compass // AR HUD

**Navegación AR Cyberpunk** con brújula digital, GPS, y scanner QR integrado. Interfaz táctica estilo Sci-Fi con feedback visual agresivo para navegación en tiempo real.

## 🌟 Características Principales

### Core Features
- **🎯 AR HUD Cyberpunk:** Interfaz visual estilo táctico con efectos CRT, scanlines, y vignette
- **🧭 Brújula Digital:** Anillo de navegación reactivo usando `DeviceOrientation API`
- **📍 Navegación GPS:** Cálculo de distancia y rumbo (bearing) hacia coordenadas objetivo
- **📷 Scanner QR Integrado:** Detección de objetivos mediante códigos QR (formato JSON)
- **🗺️ Creador de Objetivos:** Mapa interactivo (Leaflet) para generar QR de ubicaciones
- **🔒 Privacidad Total:** Todo el procesamiento ocurre en el cliente (browser)

### Advanced Features
- **📜 Historial de Objetivos:** Guarda los últimos 10 objetivos escaneados en `localStorage`
- **📤 Compartir Ubicación:** Genera QR de tu posición actual para compartir
- **🌓 Modo Día/Noche:** Adaptación automática de colores según preferencia del sistema
- **🎨 Feedback Visual de Proximidad:**
  - Distancia con código de colores (rojo <10m, naranja <50m, cyan <100m)
  - Barra de progreso de proximidad
  - Advertencias textuales ("ARRIVED!", "VERY CLOSE", "APPROACHING")
  - Flash de pantalla en umbrales críticos

### Environmental Effects
- **❄️ Ice Mode (>100m):** Efecto de escarcha con overlay de textura real
- **💧 Melt Mode (40-100m):** Bordes azules con efecto de lluvia CSS
- **🔥 Heat Mode (<40m):** Bordes rojos, pulso del anillo, efecto de calor

## 📱 Uso

1. **Escanear Objetivo:**
   - Abre la app y otorga permisos de cámara
   - Escanea un QR con formato: `{"lat": -34.6037, "lon": -58.3816, "name": "Obelisco"}`
   - Sigue la flecha en el HUD hacia tu destino

2. **Crear Objetivo:**
   - Toca "CREATE TARGET"
   - Arrastra el mapa para centrar el objetivo
   - Genera y comparte el QR

3. **Compartir Ubicación:**
   - Toca "SHARE MY LOCATION"
   - Comparte el QR generado por WhatsApp/Telegram

4. **Ver Historial:**
   - Toca "HISTORY"
   - Selecciona un objetivo previo para re-navegar

## 🚀 Despliegue

### GitHub Pages (Recomendado)
1. Ve a `Settings > Pages` en tu repositorio
2. Selecciona la rama `main` como fuente
3. Accede a `https://tu-usuario.github.io/Brujula-QR/`

> **⚠️ HTTPS Obligatorio:** Los navegadores bloquean cámara y sensores en HTTP.

### Local Development
```bash
# Servidor local simple
python -m http.server 8000
# Accede a http://localhost:8000
```

Para testing en móvil local, usa `ngrok` o similar para HTTPS.

## 🛠 Tecnologías

- **Frontend:** HTML5, CSS3 (Variables, Animations, Grid)
- **JavaScript:** Vanilla ES6+ (No frameworks)
- **APIs:**
  - `DeviceOrientation API` (Brújula)
  - `Geolocation API` (GPS)
  - `MediaDevices API` (Cámara)
  - `Web Share API` (Compartir QR)
- **Librerías:**
  - [jsQR](https://github.com/cozmo/jsQR) - Decodificación QR
  - [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) - Generación QR
  - [Leaflet](https://leafletjs.com/) - Mapas interactivos

## 📋 Formato QR

```json
{
  "lat": -34.603722,
  "lon": -58.381592,
  "name": "TGT-1234-5678"
}
```

## 🍎 Compatibilidad iOS

**Limitaciones conocidas:**
- ❌ `navigator.vibrate()` bloqueado por Apple
- ❌ Web Audio API requiere interacción del usuario
- ✅ **Solución:** Feedback visual agresivo (colores, flash, barras)

**Navegadores en iOS:** Todos usan WebKit (Safari, Chrome, Firefox en iOS son básicamente Safari con otra interfaz).

## 🎮 Controles

- **Scan Screen:** Escanear QR, crear objetivo, ver historial
- **Compass Screen:** Navegación AR con HUD completo
- **Create Screen:** Mapa interactivo con crosshair central
- **CANCEL NAV:** Volver a pantalla de escaneo

## 📊 Métricas HUD

- **DIST:** Distancia al objetivo (metros)
- **BRNG:** Bearing/rumbo al objetivo (0-360°)
- **HDNG:** Heading/orientación del dispositivo (0-360°)

## 🔧 Desarrollo

El proyecto es un **single HTML file** para máxima portabilidad:
- `index.html` - Aplicación completa (HTML + CSS + JS)
- `jsQR.js` - Librería QR vendorizada localmente
- `overlay_ice.png` - Textura de escarcha (opcional)

---

**Desarrollado como prototipo de concepto de navegación AR sin apps nativas.**

🚀 **Live Demo:** [https://a-martyniuk.github.io/Brujula-QR/](https://a-martyniuk.github.io/Brujula-QR/)

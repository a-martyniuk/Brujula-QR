# QR Compass // AR HUD

![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)
![Tech](https://img.shields.io/badge/Stack-HTML5%20%7C%20CSS3%20%7C%20JS-orange?style=for-the-badge)

**Navegación AR Cyberpunk** con brújula digital, GPS y scanner QR integrado. Una interfaz táctica estilo Sci-Fi con feedback visual agresivo diseñada para la navegación en tiempo real directamente desde el navegador.

---

## 🌟 Características Principales

### Core Features
- **🎯 AR HUD Cyberpunk:** Interfaz visual inmersiva con efectos CRT, scanlines y viñeteado.
- **🧭 Brújula Digital:** Anillo de navegación reactivo utilizando la `DeviceOrientation API`.
- **📍 Navegación GPS:** Cálculo preciso de distancia y rumbo hacia coordenadas objetivo.
- **📷 Scanner QR Integrado:** Detección instantánea de objetivos mediante códigos QR JSON.
- **🗺️ Creador de Objetivos:** Mapa interactivo con tecnología Leaflet para generar puntos de interés.
- **🔒 Privacidad Total:** Procesamiento 100% en el cliente (Client-Side).

### Advanced Features
- **📜 Historial Local:** Almacenamiento de los últimos 10 objetivos .
- **📤 Compartir Ubicación:** Generación de QR de posición actual para compartir rápidamente.
- **🌓 Modo Día/Noche:** Adaptación automática del esquema de colores.
- **🎨 Feedback Visual de Proximidad:**
  - Código de colores por distancia (Rojo <10m, Naranja <50m, Cyan <100m).
  - Alertas visuales y textuales inmersivas.

### Environmental Effects
- **❄️ Ice Mode (>100m):** Efecto de escarcha con superposición de texturas.
- **💧 Melt Mode (40-100m):** Efecto de lluvia y deshielo en la interfaz.
- **🔥 Heat Mode (<40m):** Pulso de calor y bordes de advertencia rojos.

## 🛠 Tecnologías

Este proyecto está construido con tecnologías web modernas, sin dependencias pesadas de frameworks, asegurando máxima portabilidad y rendimiento.

*   **Frontend:** HTML5, CSS3 (Variables, Animations, Grid).
*   **Lógica:** JavaScript (Vanilla ES6+).
*   **APIs Web:**
    *   `DeviceOrientation API` (Orientación)
    *   `Geolocation API` (Posición)
    *   `MediaDevices API` (Cámara)
    *   `Web Share API` (Compartir)
*   **Librerías:**
    *   [jsQR](https://github.com/cozmo/jsQR) (Decodificación QR)
    *   [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) (Generación QR)
    *   [Leaflet](https://leafletjs.com/) (Mapas)

## 📱 Uso

1.  **Escanear Objetivo:**
    *   Abre la aplicación y concede permisos de cámara.
    *   Escanea un código QR con el formato JSON compatible.
    *   Sigue la flecha en el HUD hacia tu destino.

2.  **Crear Objetivo:**
    *   Toca "CREATE TARGET".
    *   Selecciona la ubicación en el mapa.
    *   Genera y guarda el QR.

3.  **Compartir Ubicación:**
    *   Toca "SHARE MY LOCATION" para generar un QR de tu posición actual.

## 📋 Formato JSON del QR

Para crear tus propios códigos QR compatibles manualmente:

```json
{
  "lat": -34.603722,
  "lon": -58.381592,
  "name": "Nombre Del Objetivo"
}
```

## 🚀 Despliegue

### Local
Simplemente sirve el directorio con cualquier servidor HTTP (requerido para permisos de cámara/sensores).

```bash
# Ejemplo con Python
python -m http.server 8000
```
Accede a `http://localhost:8000`. **Nota:** Para probar en móvil, necesitarás HTTPS (puedes usar ngrok).

### GitHub Pages
Configurado para funcionar directamente desde la rama `main` en GitHub Pages.

---
**Desarrollado como prototipo de navegación AR ligera.**

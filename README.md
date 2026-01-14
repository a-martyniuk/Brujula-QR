# QR Compass // AR HUD

Experimentación de navegación WebAR utilizando sensores del dispositivo (Giroscopio/GPS) para orientación en tiempo real sin aplicaciones nativas.

## 🌟 Características

*   **Cyberpunk AR HUD:** Interfaz visual estilo Sci-Fi/Tactical.
*   **Brújula Digital:** Anillo de navegación reactivo usando `DeviceOrientation`.
*   **Navegación GPS:** Cálculo de distancia y rumbo (Bearing) hacia coordenadas objetivo.
*   **Scanner QR Integrado:** Detección de objetivos mediante códigos QR (Formato JSON o lat,lon).
*   **Privacidad:** Todo el procesamiento ocurre en el cliente (Browser).

## 🚀 Despliegue y Testing

Para probar la aplicación en un dispositivo móvil, es **obligatorio usar HTTPS**, ya que los navegadores bloquean el acceso a la cámara y sensores en conexiones inseguras (HTTP).

### Opción Recomendada: GitHub Pages
1.  Ve a `Settings > Pages` en tu repositorio.
2.  Selecciona la rama `main` como fuente.
3.  Accede a la URL generada (ej: `https://tu-usuario.github.io/Brujula-QR/`).

### Opción Local (Solo Desarrollo)
Si necesitas probar localmente en tu PC:
1.  Usa `localhost` (los navegadores lo tratan como seguro).
2.  Para móvil en red local, necesitarás configurar un proxy HTTPS o usar herramientas como `ngrok`.

## 🛠 Tecnologías

*   HTML5 / CSS3 (Variables, Animations)
*   Vanilla JavaScript (ES6+)
*   [jsQR](https://github.com/cozmo/jsQR) para decodificación de video.

## 📱 Uso

1.  Abre la aplicación.
2.  Otorga permisos de cámara.
3.  Escanea un código QR con coordenadas (ej: `{"lat": -34.6037, "lon": -58.3816, "name": "Obelisco"}`).
4.  Sigue la flecha en el HUD hacia tu destino.

---
*Desarrollado como prototipo de concepto.*

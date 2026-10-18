# PIXEL PARK — simulador IoT de estacionamiento

Sitio estático en HTML, CSS y JavaScript puro listo para Vercel.

## Ejecutar
Abre `index.html` en un navegador con Internet para descargar las librerías de QR y MQTT.

## Desplegar en Vercel
1. Sube esta carpeta a GitHub.
2. En Vercel, **Add New > Project**, importa el repositorio.
3. Framework Preset: **Other**, Build Command: vacío y Output Directory: vacío (raíz).
4. Pulsa Deploy.

Alternativa: usar Vercel CLI desde esta carpeta (`npx vercel`).

## Funcionalidades
- 8 plazas con carros pixel art y movimientos animados.
- Cada 60 s alterna entre 1 y 3 plazas y simula distancia en centímetros.
- Distancia >= 100 cm: LIBRE. Distancia < 100 cm: OCUPADA.
- QR nuevo por ciclo con enlace al sitio y los estados del momento; **no** representa datos sincronizados entre dispositivos si no hay broker.
- Botones de prueba para demostrar LIBRE y OCUPADA.
- Mensaje `{ plaza, distancia, estado, timestamp }` por tópico `universidad/parking/plaza01` etc.
- MQTT real opcional a través de WebSocket seguro con broker público de ejemplo `wss://broker.emqx.io:8084/mqtt` (requiere conectividad, acceso del broker y soporte de WebSockets).
- Suscriptor dentro de la página que muestra eventos recibidos.

**Nota:** El broker público puede ser compartido y no garantiza privacidad, exclusividad ni disponibilidad. Para despliegue real, utiliza un broker privado/autenticado y tópicos únicos.

## Dependencias CDN
- qrcode-generator 1.4.4
- MQTT.js 5.14.1
- Google Fonts (opcional)
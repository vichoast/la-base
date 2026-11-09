# La Base 2.0

Juego de construir en 3D isométrico que premia **partir** con las tareas: casa y aseo, U y práctica, y pendientes sueltos. Es una app web instalable (PWA): en Android queda con ícono propio, a pantalla completa y funciona sin internet.

## Archivos

| Archivo | Qué es |
|---|---|
| `index.html` | Toda la app: estilos, pixel art, misiones y lógica |
| `sw.js` | Service worker: guarda la app para usarla sin internet y abre la app al tocar un aviso |
| `manifest.webmanifest` | Nombre, colores e íconos para instalarla |
| `icons/` | Íconos en pixel art (192, 512 y versión "maskable" para Android) |
| `serve.ps1` | Servidor local para probarla en el PC: `http://localhost:5173` |

## Probarla en el PC

```
powershell -ExecutionPolicy Bypass -File serve.ps1
```

## Instalarla en el celular

Para instalarla, Android necesita que la app esté en una dirección **https**. El camino más simple es GitHub Pages, igual que el sitio del Restaurant San José:

1. Sube esta carpeta a un repositorio de GitHub.
2. En el repo: Settings → Pages → Branch `main` → carpeta `/ (root)`.
3. Abre la dirección en Chrome del celu → menú ⋮ → **Instalar app**.

## Qué cambió respecto de La Base 1

- El mundo sigue siendo el isométrico 3D de La Base 1 (los mismos 12 edificios, la noche y el faro). La interfaz tiene toques retro: títulos en pixel, el Maestro y los íconos en pixel art.
- Zona nueva **U y práctica** (8 misiones) y filtro para elegir Todo, Casa y aseo, o U y práctica.
- **Pendientes sueltos**: anotas algo sin hora y, cuando lo haces, suma ladrillos.
- **Avisos** de celular: inactividad, fin del timer y cierre del día. Por ahora llegan solo mientras la app sigue abierta o en segundo plano.
- La pantalla no se apaga durante una misión. El celular vibra al marcar pasos. Los sonidos y la música son los mismos de La Base 1, más uno nuevo en la misma onda (dos notas suaves al anotar un pendiente, elegir edificio o subir de nivel).
- Respaldo: descargar y cargar un archivo `.json` (sirve también para pasar la base a otro celular).

## Traer tu avance de La Base 1

Tu avance de La Base 1 vive en el navegador donde abres `La Base.html` (en el Escritorio).

1. En el Escritorio, abre `traer-avance.html` en el mismo navegador. Muestra tus misiones, ladrillos y edificios.
2. Toca "Descargar respaldo".
3. En La Base 2.0: Ajustes, luego "Cargar respaldo", y elige ese archivo.

Si abres La Base 2.0 en el mismo navegador y todavía no tiene datos, trae el avance de La Base 1 sola.

## Lo que viene (fase siguiente)

- Avisos con la app cerrada, usando Firebase Cloud Messaging (necesita un servidor chico que mande los avisos).
- Guardado en la nube para ver el mismo avance en el PC y en el celular.

# 🔮 Calculadora de Estimación "Aurora"

¡Bienvenido/a! Estás ante la **Calculadora Aurora**, una pequeña pero potente herramienta web diseñada para calcular cuándo estará lista una tarea basándose en los horarios reales de tu equipo.

Este proyecto ha sido diseñado con mucho mimo (y una filosofía *Mobile-First* muy estricta) para que funcione genial tanto en tu móvil como en tu ordenador.

---

## 🚀 ¿Qué hace esto?

Imagina que tienes una tarea que dura **8 horas**.
Y se la asignas a **Ana**, que trabaja de 9:00 a 17:00, pero hoy ya son las 15:00.
¿Cuándo terminará Ana?

La calculadora no solo suma 8 horas al reloj. Tiene en cuenta:
1.  **Horarios de turno**: Si Ana sale a las 17:00, la tarea se pausa y continúa mañana a las 9:00.
2.  **Fines de semana**: Si mañana es sábado y Ana no trabaja, salta al lunes.
3.  **Festivos**: ¡Sí, también sabe cuándo es Navidad!

---

## 👶 Para Principiantes: ¿Cómo lo uso?

¡Es súper fácil! No necesitas instalar nada complicado.

1.  **Descarga** este código.
2.  Busca el archivo `index.html`.
3.  Haz **doble clic** en él.
4.  ¡Ya está! Se abrirá en tu navegador (Chrome, Firefox, Edge...).

### ¿Quieres cambiar cosas?
*   **Colores y Diseño**: Todo el estilo visual está en `index.html`. Usamos **Tailwind CSS** (vía CDN), así que verás muchas clases tipo `text-blue-500` o `p-4`. ¡Prueba a cambiarlas!
*   **Textos**: Busca cualquier texto en el `index.html` y cámbialo por lo que quieras.

---

## 🤓 Para Nivel Medio: ¿Cómo funciona por dentro?

Todo el cerebro está en `app.js`. Aquí tienes un mapa rápido:

### 1. La Base de Datos (`WorkerDatabase`)
Al principio del archivo verás un objeto gigante con los trabajadores.
```javascript
"A101": {
    name: "Ana Martínez",
    schedule: { ... } // Aquí definimos sus turnos
}
```
**Reto**: ¡Intenta añadirte a ti mismo como trabajador con tu propio horario!

### 2. El Motor de Tiempo (`calculateEstimation`)
Esta función es la joya de la corona.
*   Toma la fecha de inicio (ahora).
*   Va restando minutos a la tarea minuto a minuto (bueno, en saltos lógicos).
*   Si llega al final del turno del trabajador, utiliza `jumpToNextShift` para "saltar" hasta la próxima mañana laborable.

### 3. La Interfaz "Bento" (`UI Controller`)
Usamos una arquitectura orientada a eventos sencilla.
*   **Mobile-First**: Si miras el código, verás que todo está pensado primero para pantallas pequeñas y luego usamos `md:` para ampliarlo en PC.
*   **Efecto Teatro**: Hemos programado la app para que **no calcule nada** hasta que pulsas el botón grande. Si intentas pulsar sin datos... ¡verás una animación de "shake" (temblor) advirtiéndote!

---

## 🎨 Estructura de Archivos

*   `index.html`: El esqueleto y la piel (HTML + Tailwind CSS).
*   `app.js`: El cerebro y los músculos (Lógica Javascript).
*   `README.md`: Este manual que estás leyendo.

---

¡Disfruta trasteando con el código! 
Si rompes algo, no te preocupes, para eso está `Ctrl + Z`. 😉

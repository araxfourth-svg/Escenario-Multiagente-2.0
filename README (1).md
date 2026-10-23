# 🌳🦉🤖 Charla en el monte — escenario multiagente

Don Algarrobo, el Profesor Lechu y Botín charlan por turnos sobre la naturaleza de Formosa, en el escenario de Don Algarrobo. Personajes ficticios creados con inteligencia artificial.

## Cómo funciona
- Cada personaje tiene su propio agente de ElevenLabs y su propia voz.
- Hablan **de a uno**: la página abre la conexión de un agente, le hace decir la línea del guion (con el «primer mensaje» como override), espera a que termine, la cierra y recién entonces pasa al siguiente. Nunca hay dos voces a la vez.
- El micrófono queda silenciado. El navegador pide permiso igual porque el SDK de voz lo exige.
- El guion está en `index.html`, constante `GUION`. Editando esas líneas cambia la charla.

## Requisito en cada agente
En ElevenLabs, el agente debe permitir el override del primer mensaje (**Agent → Security → Overrides → First message**) y no tener autenticación activada.
- Don Algarrobo y Profesor Lechu: ya está habilitado.
- **Botín (otra cuenta): hay que habilitarlo desde esa cuenta.** Si no está, la página hace hablar a Botín con la voz del navegador y lo avisa en pantalla.

## Publicar en GitHub Pages
1. Subí `index.html` a un repositorio (por ejemplo `escenario-multiagente`).
2. **Settings → Pages → Deploy from a branch → `main` / `(root)` → Save**.
3. Queda en `https://TU-USUARIO.github.io/escenario-multiagente/`.

## Guía de prueba
1. Abrí la página con `https://` y tocá **Comenzar la charla**; aceptá el permiso de audio.
2. Verificá que hablen en orden Algarrobo → Lechu → Botín…, sin pisarse, y que el pico, la boca y la pantalla de Botín acompañen la voz.
3. Mirá si aparece el aviso de voz del navegador (señal de que un agente no aceptó el mensaje; abrí la consola con F12).
4. **Detener** corta la charla; **Ver de nuevo** la repite.

## Estado
- Probado: solo la sintaxis del código. La conexión con los tres agentes y la sincronización de las voces falta verificarla en un navegador real.

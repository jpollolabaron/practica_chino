# 🇨🇳 中文 · Práctica de chino

Aplicación web estática para practicar **chino mandarín nivel HSK 1** mediante vocabulario, frases y reconocimiento auditivo.

Funciona directamente en el navegador: no necesita servidor, base de datos ni dependencias.

## Modos de práctica

### 🀄 Vocabulario HSK 1

Incluye la lista clásica de **150 palabras HSK 1**, organizada en **15 lotes temáticos de 10 palabras** para facilitar repasos cortos y frecuentes.

Cada tarjeta muestra desde el inicio:

- hanzi;
- pinyin;
- botón de audio en mandarín.

Al revelar la respuesta aparecen:

- significado en español;
- frase breve de ejemplo;
- pinyin del ejemplo;
- traducción al español.

Es posible seleccionar uno o varios lotes a la vez. De esta forma se puede comenzar con 10 palabras y ampliar progresivamente la ronda.

### 💬 Frases HSK 1

Dos lecciones de 20 frases:

- **Lección 1: Primeras frases** — saludos, presentación, familia, gustos, números y expresiones básicas.
- **Lección 2: Frases en contexto** — preguntas, ubicación, horarios, compras, clima y acciones cotidianas.

Las frases muestran hanzi y pinyin desde el inicio y permiten escuchar la pronunciación.

### 🎧 Reconocimiento por audio

La frase se mantiene oculta inicialmente.

1. Se escucha el audio.
2. Se intenta reconocer la frase.
3. Se pulsa **Mostrar respuesta**.
4. Aparecen hanzi, pinyin y significado.
5. Se marca como **La sabía** o **No la sabía**.

## Repaso

En cualquier modalidad, las tarjetas marcadas como **No la sabía** se agregan a una cola de repaso.

Al finalizar la ronda es posible practicar únicamente esas tarjetas pendientes.

## Audio

La aplicación utiliza la Web Speech API del navegador mediante `SpeechSynthesis` y solicita una voz en chino mandarín:

```javascript
utterance.lang = "zh-CN";
```

Se puede elegir la velocidad de reproducción:

- 0.6x
- 0.8x
- 1.0x
- 1.2x
- 1.4x

La calidad de la voz depende del navegador y del sistema operativo.

## Ejecución

No requiere instalación. Basta con abrir:

```text
index.html
```

en un navegador moderno.

También puede ejecutarse con un servidor web local:

```bash
python -m http.server 8000
```

Luego abrir:

```text
http://localhost:8000
```

## GitHub Pages

El proyecto puede publicarse directamente con GitHub Pages:

1. Subir `index.html`, `README.md` y `favicon.svg` al repositorio.
2. Ir a **Settings → Pages**.
3. En **Build and deployment**, elegir **Deploy from a branch**.
4. Seleccionar la rama `main`.
5. Seleccionar `/ (root)`.
6. Guardar.

## Estructura

```text
/
├── index.html
├── favicon.svg
└── README.md
```

Toda la interfaz, los datos y la lógica principal están contenidos actualmente en `index.html`.

## Tecnologías

- HTML5
- CSS3
- JavaScript
- Web Speech API (`SpeechSynthesis`)
- `localStorage`

No utiliza frameworks ni librerías externas.

## Objetivo

La aplicación busca facilitar una progresión simple:

**reconocer palabras → asociar hanzi y pinyin → comprender el significado → verlas dentro de frases → reconocerlas por audio.**

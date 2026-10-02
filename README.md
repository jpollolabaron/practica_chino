# Práctica de chino — HSK 1

Aplicación web sencilla para practicar frases de **chino mandarín nivel HSK 1** mediante tarjetas y ejercicios de reconocimiento auditivo.

El proyecto funciona directamente en el navegador y no necesita servidor, base de datos ni instalación de dependencias.

## Características

- 2 lecciones de HSK 1.
- 20 frases por lección.
- Hanzi y pinyin visibles desde el inicio en el modo tarjetas.
- Traducción al español.
- Frases de ejemplo con hanzi, pinyin y traducción.
- Reproducción de audio en chino mandarín.
- Control de velocidad de audio:
  - 0.6x
  - 0.8x
  - 1.0x
  - 1.2x
  - 1.4x
- Modo de práctica con tarjetas.
- Modo de reconocimiento por audio.
- Botones **La sabía** y **No la sabía**.
- Cola automática de repaso para las frases que cuestan más.
- Progreso de la ronda.
- Guardado temporal del estado mediante `localStorage`.
- Diseño adaptable a computadora y dispositivos móviles.

## Lecciones

### HSK 1 — Lección 1: Primeras frases

20 frases iniciales para practicar:

- saludos;
- presentación personal;
- familia;
- profesiones;
- gustos;
- comida y bebida;
- números;
- días de la semana;
- horas;
- expresiones básicas como 谢谢, 对不起 y 再见.

### HSK 1 — Lección 2: Frases en contexto

20 frases un poco más avanzadas con:

- preguntas;
- lugares y ubicación;
- horarios;
- compras y precios;
- clima;
- acciones cotidianas;
- estudio;
- trabajo;
- uso de 会, 能 y 想.

## Modos de práctica

### Tarjetas

La frase aparece desde el comienzo con:

- 汉字 (hanzi);
- pinyin;
- botón para escuchar la pronunciación.

Al mostrar la respuesta se puede consultar también:

- significado en español;
- frase de ejemplo;
- pinyin del ejemplo;
- traducción del ejemplo.

Después se puede marcar la frase como:

- **La sabía**
- **No la sabía**

Las frases marcadas como no conocidas se agregan a la ronda de repaso.

### Audios

En este modo la frase permanece oculta inicialmente.

1. Se escucha el audio.
2. Se intenta reconocer la frase.
3. Se selecciona **Mostrar respuesta**.
4. Aparecen hanzi, pinyin y significado.
5. Se indica si la frase era conocida o debe repasarse.

## Audio

La aplicación utiliza la API `SpeechSynthesis` del navegador.

La voz se configura como:

```javascript
utterance.lang = "zh-CN";
```

Cuando el navegador dispone de una voz china instalada, la aplicación intenta seleccionarla automáticamente.

> La calidad y disponibilidad de las voces puede variar según el navegador y el sistema operativo.

## Uso

No requiere instalación.

Descargá o cloná el repositorio:

```bash
git clone URL_DEL_REPOSITORIO
```

Después abrí:

```text
index.html
```

en un navegador moderno.

También se puede ejecutar con un servidor web local, por ejemplo:

```bash
python -m http.server 8000
```

y abrir:

```text
http://localhost:8000
```

## Publicación con GitHub Pages

El proyecto puede publicarse directamente con GitHub Pages.

1. Subir `index.html` al repositorio.
2. Ir a **Settings → Pages**.
3. En **Build and deployment**, elegir **Deploy from a branch**.
4. Seleccionar la rama `main`.
5. Seleccionar la carpeta `/ (root)`.
6. Guardar.

GitHub generará una dirección similar a:

```text
https://usuario.github.io/nombre-del-repositorio/
```

## Estructura

```text
/
├── index.html
├── favicon.svg
└── README.md
```

Toda la lógica principal de la aplicación, las frases y los estilos están actualmente contenidos en `index.html`.

## Datos de las frases

Las lecciones se encuentran definidas dentro de `APP_DATA`:

```javascript
const APP_DATA = {
  lessons: [
    // ...
  ]
};
```

Cada frase utiliza una estructura similar a:

```javascript
{
  "id": "hsk01-l1-001",
  "hanzi": "你好。",
  "pinyin": "Nǐ hǎo.",
  "meaning": "Hola.",
  "example_hanzi": "你好，我叫王明。",
  "example_pinyin": "Nǐ hǎo, wǒ jiào Wáng Míng.",
  "example_es": "Hola, me llamo Wang Ming."
}
```

Esto permite agregar nuevas lecciones o frases sin modificar la lógica principal de la aplicación.

## Tecnologías

- HTML5
- CSS3
- JavaScript
- Web Speech API (`SpeechSynthesis`)
- `localStorage`

No utiliza frameworks ni librerías externas.

## Objetivo

El objetivo del proyecto es ofrecer una herramienta simple para practicar chino mandarín, especialmente:

- reconocimiento de caracteres;
- asociación entre hanzi y pinyin;
- comprensión de frases;
- pronunciación;
- reconocimiento auditivo;
- repaso de vocabulario HSK 1.

## Licencia

Proyecto de práctica y estudio personal.

Podés modificar esta sección si decidís publicar el proyecto con una licencia específica, por ejemplo MIT.

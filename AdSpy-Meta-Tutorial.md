# AdSpy Meta — Tutorial

AdSpy Meta te ayuda a **encontrar anuncios** en la Biblioteca de anuncios de Meta (Facebook e Instagram), **analizarlos con IA** y **guardar los mejores** para inspirarte.

Puedes usarla de dos formas, sin instalar nada:
- **En línea:** desde Herramix, botón **USAR GRATIS AHORA**.
- **En tu PC:** descarga el `.zip`, descomprímelo y abre `index.html` con doble clic en Chrome o Edge.

---

## 1. Antes de empezar (solo la primera vez)

### 1.1 Ollama: la IA en tu PC

La app usa **Ollama** para analizar los anuncios. Ollama funciona en tu PC, es gratis y **no necesita internet**.

1. Abre **Ollama**. Sabrás que está abierto porque aparece el icono de la llama junto al reloj.
2. Ten al menos un modelo descargado. Recomendado:

   ```
   ollama pull gemma3:4b
   ```

   - Pesa unos 3,3 GB, escribe bien en español y **lee imágenes**, así que también analiza las capturas.
   - Si la descarga se corta, vuelve a escribir el mismo comando y sigue donde se quedó.
   - Cualquier otro modelo también funciona. Si no lee imágenes (por ejemplo `qwen2.5-coder:7b`), la app analiza solo el texto y te lo avisa.

### 1.2 Conectar la app con Ollama

1. Abre `index.html` en Chrome.
2. Ve a la pestaña **🧠 Analizar**.
3. Debajo de los botones, abre el panel **🤖 Motor de IA**.
4. En **Usar**, deja **Ollama**.
5. Pulsa **↻ Buscar**: aparecen los modelos que tienes instalados.
6. Elige uno y pulsa **Guardar**.

Cuando está bien configurado, el panel muestra una etiqueta verde con el modelo, por ejemplo `Ollama · gemma3:4b`.

> **Si usas la versión en línea**, la primera vez el navegador puede preguntar si permites que la página acceda a otras apps o a la red local de tu dispositivo. Pulsa **Permitir**: es la conexión con Ollama en tu PC.

> **Si sale "No se pudo conectar con Ollama"** aunque Ollama esté abierto:
> 1. Cierra Ollama (clic derecho en el icono de la llama → Quit).
> 2. Abre el **Símbolo del sistema** y escribe:
>    ```
>    setx OLLAMA_ORIGINS "*"
>    ```
> 3. Vuelve a abrir Ollama y pulsa **↻ Buscar** en la app.
>
> Solo se hace una vez.

### 1.3 (Opcional) Usar OpenAI en lugar de Ollama

1. En **🤖 Motor de IA**, cambia **Usar** a **OpenAI**.
2. Pega tu **clave API** (empieza por `sk-`).
3. Pulsa **Probar conexión**: se carga la lista de modelos de tu cuenta.
4. Elige el modelo y pulsa **Guardar**.

Necesita internet (con la VPN activa) y gasta saldo de tu cuenta de OpenAI.

---

## 2. Pestaña 🔎 Buscar — encontrar anuncios

Aquí preparas la búsqueda. La app arma el enlace a la Biblioteca de Meta con todos tus filtros.

| Filtro | Para qué sirve |
|---|---|
| **Palabra clave** | El tema: "envío gratis", "curso online", "inmobiliaria"… |
| **Buscar la frase exacta** | Solo anuncios con esas palabras juntas y en ese orden. |
| **Palabras rápidas** | Botones con temas frecuentes; un clic y se rellena la palabra clave. |
| **Anunciante** | Para ver *todos* los anuncios de una marca. Pega el enlace de su página en la Biblioteca de Meta o su número de ID. |
| **País** | Dónde se muestran los anuncios. |
| **Idioma** | Idioma del anuncio. |
| **Estado** | Activos ahora, inactivos o ambos. |
| **Formato** | Imagen, video, meme o solo texto. |
| **Orden** | Más impresiones primero (los que más se ven) o más relevantes. |
| **Plataformas** | Facebook, Instagram, Messenger, Threads, Audience Network. |
| **Empezaron a circular** | Última semana, mes, 3 meses, año, o tus propias fechas **Desde / Hasta**. |

### Cómo buscar

1. Escribe la palabra clave y ajusta los filtros.
2. Pulsa **↗ Abrir en la Biblioteca de Meta**. Se abre Meta en otra pestaña con los resultados.
3. Busca el anuncio que te interese.

Otros botones:
- **⧉ Copiar enlace**: copia la búsqueda para mandarla por WhatsApp o guardarla.
- **↺ Limpiar filtros**: vuelve a los valores iniciales.
- **Búsquedas recientes**: tus últimas búsquedas. Pulsa **Usar** para repetir una con los mismos filtros.

> **Consejo — anuncios para Cuba:** Meta casi no muestra anuncios *dentro* de Cuba, así que con el país "Cuba" la búsqueda puede salir vacía. Los negocios que venden hacia Cuba se anuncian desde fuera. Pon el país en **Estados Unidos** o **Todos** y usa palabras como "envíos a Cuba", "combos Cuba", "recargas Cubacel", "Habana" u "Holguín".

---

## 3. Pestaña 🧠 Analizar — puntuar y mejorar un anuncio

### 3.1 Pasar el anuncio a la app

En Meta, toca **Ver detalles del anuncio** y copia lo que necesites.

| Campo | ¿Obligatorio? |
|---|---|
| **Texto principal** | Sí, salvo que subas el video del anuncio. Es el texto largo del anuncio. |
| **Marca** | No, pero ayuda. |
| **Titular** | No. Es la línea en negrita junto al botón. |
| **Botón (CTA)** | No. Elige el que tiene el anuncio. |
| **Objetivo** | No. Qué busca el anuncio: ventas, mensajes, etc. |
| **Tono de las nuevas versiones** | Cómo quieres que suenen los textos que proponga la IA. |
| **Imagen o video del anuncio** | No. Arrástralo a la zona punteada o usa **🖼 Elegir imagen** / **🎬 Elegir video**. Una captura (por ejemplo, hecha con FireShot) o el video del anuncio. Requiere un modelo con visión. Ver el apartado 3.2. |

### 3.2 Anuncios en video

Si el anuncio es un video, súbelo con **🎬 Elegir video** o arrástralo a la zona punteada. Sirve el video que descargaste o una grabación de pantalla que hiciste del anuncio. Formatos: MP4, MOV o WEBM.

La app lo procesa en tu PC, sin internet, en unos segundos:

- **8 fotogramas clave**: 3 de los **primeros 3 segundos** (el gancho, marcados en celeste) y 5 repartidos hasta el final.
- **Medidas del ritmo**: duración, número de escenas, cada cuántos segundos hay un corte, cortes en los primeros 3 segundos y formato (vertical, horizontal o cuadrado).

Al pulsar **Analizar y mejorar**, la IA mira los fotogramas junto con esas medidas y añade al resultado:
- **Gancho (0-3 s)**: si detiene el scroll y cómo mejorarlo.
- **Ritmo y edición**.
- **Guion mejorado**: un video nuevo de 15 a 30 segundos, escena por escena (segundos, lo que se ve, texto en pantalla y lo que se dice).

Con **3 versiones nuevas**, cada versión trae también un guion corto de 15 segundos.

> **La voz:** la IA ve las imágenes pero **no escucha el audio**. Si el video tiene locución, pega lo que dice en **Lo que se dice en el video** (puedes sacarlo con tu herramienta de subtítulos). Sin eso, analiza solo lo visual y el texto en pantalla.
>
> **Modelo:** para videos necesitas un modelo con visión, como `gemma3:4b`. Con uno sin visión, la app analiza solo las medidas y el texto, y te lo avisa.

**Quitar video** lo descarta. Si subes una imagen, el video se quita (se analiza una cosa a la vez).

### 3.3 Botones

- **🧠 Analizar y mejorar** — Da:
  - **Notas de 0 a 100** en Gancho, Oferta, Confianza, CTA y una nota **Global**. Verde = bien (75+), azul = regular (50–74), rojo = flojo (menos de 50).
  - **Diagnóstico**: estilo, emoción principal y a quién va dirigido.
  - **Lo que funciona** y **Lo que falla** (con ejemplos de *antes → después*).
  - **Riesgos con las políticas de Meta**.
  - **Versión mejorada**, lista para usar.
- **✍️ 3 versiones nuevas** — Tres textos distintos del mismo anuncio, cada uno con otro gancho, y cuál probar primero.
- **Limpiar** — Vacía el formulario.

El texto aparece mientras la IA escribe. Con Ollama puede tardar de unos segundos a un par de minutos, según el modelo y tu PC.

### 3.4 Qué hacer con el resultado

- **💾 Guardar** — Lo guarda en la pestaña Guardados, con el texto, el análisis y las notas. Los anuncios en video aparecen con 🎬 y su duración (se guardan los datos y el análisis, no el video).
- **⧉ Copiar** — Copia el resultado para pegarlo donde quieras.
- **⬇ Descargar** — Descarga un archivo `.md` con el anuncio y su análisis.
- **🎬 Crear el video →** — Copia la versión mejorada (o el guion, si analizaste un video) y abre **AUREA Studio**, donde lo pegas para convertirlo en un anuncio en video con narración y subtítulos.

### 3.5 (Opcional) Lectura automática con el enlace del anuncio

En lugar de copiar a mano, la app puede traer el anuncio desde su enlace. Usa el servicio **Apify**, que tiene saldo gratis cada mes y después es de pago.

**Activarla (una vez):**
1. Crea una cuenta en **apify.com**.
2. Ve a **Settings → API & Integrations** y copia tu **clave API**.
3. En Analizar, abre **⚙️ Lectura automática**, pega la clave y pulsa **Guardar**.

**Usarla:**
1. Copia el enlace del anuncio en Meta (del tipo `facebook.com/ads/library/?id=…`).
2. Pégalo en **Enlace del anuncio en Meta** y pulsa **⚡ Traer**.
3. En 20–60 segundos se rellenan el texto, la marca, el titular, el botón y la imagen.
   - **Si es un video**, aparece el botón **⬇ Descargar el video del anuncio**. Si Meta lo permite, la app además lo carga sola para analizarlo; si no, descárgalo con ese botón y súbelo con **🎬 Elegir video**.
4. Pulsa **Analizar y mejorar**.

Si falla (clave incorrecta, saldo agotado o anuncio retirado), la app te dice el motivo y sigues copiando a mano.

---

## 4. Pestaña 💾 Guardados — tu colección

Aquí están los anuncios que guardaste. El número junto al nombre de la pestaña indica cuántos hay.

- **Buscar** — Filtra por marca o por cualquier palabra del texto.
- **Guardados en** — Muestra solo los de la última semana, mes o año.
- **Abrir** — Lo carga en Analizar con su análisis y sus notas, para revisarlo o volver a analizarlo.
- **✕** — Borra ese anuncio (te pide confirmación).
- **⬇ Exportar a Excel (CSV)** — Descarga todos tus anuncios en un archivo que abre Excel, con los acentos bien.
- **🗑 Borrar todo** — Vacía la colección. **No se puede deshacer.**

> **Importante:** todo se guarda **en el navegador de este PC**. Si borras los datos de navegación de Chrome o abres la app en otro navegador u otro PC, no verás lo guardado. Para tener una copia, usa **Exportar a Excel** de vez en cuando.

---

## 5. Flujo de trabajo recomendado

1. **Buscar**: palabra clave + "Activos ahora" + "Último mes" + "Más impresiones primero".
2. Abre Meta y revisa 5–10 anuncios. Fíjate en los que llevan **más tiempo circulando**: si un anuncio sigue activo después de semanas, probablemente le funciona al anunciante.
3. Pasa los mejores a **Analizar** y pulsa **Analizar y mejorar**.
4. **Guarda** los que tengan buena nota o ideas útiles.
5. Usa **3 versiones nuevas** para crear tus propios anuncios o los de tus clientes.
6. Repite cada semana y compara: los ganchos y formatos que se repiten son la tendencia.

> **Inspírate, no copies.** Usa los anuncios como referencia; copiar textos o imágenes de otros puede violar derechos de autor y las políticas de Meta.

---

## 6. Problemas frecuentes

| Problema | Solución |
|---|---|
| "No se pudo conectar con Ollama" | Abre Ollama. Si el navegador pregunta por la red local, pulsa **Permitir**. Si sigue, haz el paso `setx OLLAMA_ORIGINS "*"` (apartado 1.2). |
| "Primero elige el motor de IA" | Abre **🤖 Motor de IA**, pulsa **↻ Buscar**, elige un modelo y **Guardar**. |
| "No se pudo leer este video" | El formato no es compatible con el navegador. Conviértelo a **MP4 (H.264)** con tu editor de video. |
| "Este modelo no lee imágenes" / "no ve imágenes" | Es un aviso, no un error: se analizó solo el texto. Para imágenes usa `gemma3:4b`. |
| El análisis tarda mucho | Normal con modelos grandes. Prueba un modelo más pequeño o cierra otros programas pesados. |
| Las notas salen como "—" | El modelo no respondió en el formato esperado. Vuelve a pulsar **Analizar**; con `gemma3:4b` pasa menos. |
| La búsqueda en Meta sale vacía | Afloja filtros: país **Todos**, estado **Activos e inactivos**, periodo **Cualquier fecha**. |
| OpenAI da error | Revisa la clave y que la VPN esté activa. |
| No veo mis anuncios guardados | Estás en otro navegador o se borraron los datos de Chrome. Usa la exportación a Excel como copia. |

---

## ¿Necesitas ayuda?

Si algo no funciona o quieres que te acompañe en la configuración, escríbeme por WhatsApp: **+53 5508 1288**.

---

*AdSpy Meta es una herramienta gratuita de **Herramix** · Los datos vienen de la Biblioteca pública de Meta · No está afiliado a Meta · El análisis con IA es orientativo.*

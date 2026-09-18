# Sitio web de Baremo · cómo publicarlo y cómo editarlo

Sitio estático de una sola página. No usa servidor, ni base de datos, ni dependencias externas: todo (fuentes, logos, fotos) viaja dentro de esta carpeta.

## Qué hay aquí

```
index.html                 la página completa
styles.css                 todos los estilos, con los tokens del design system
assets/fonts/              IBM Plex Sans 400/600/700 y Mono 400/500 (woff2)
assets/logo/               logo sin cuadro (barra y pie) + principal (favicon)
assets/img/                4 fotos, redimensionadas y recomprimidas para web
LEEME.md                   este archivo
```

Peso total: unos 980 KB, de los cuales 825 KB son las fotos.

## Publicarlo

Sube **el contenido** de esta carpeta a la raíz del hosting de `baremo.com.co`. No subas la carpeta `sitio-baremo` en sí: el `index.html` debe quedar en la raíz del dominio, si no las rutas relativas se rompen.

- **cPanel / Hostinger / hosting tradicional:** entra al administrador de archivos, abre `public_html` y arrastra todo el contenido.
- **Netlify:** arrastra la carpeta a app.netlify.com/drop. Queda publicada al instante; después conectas el dominio.
- **GitHub Pages:** sube el contenido a la raíz de un repo y activa Pages sobre la rama `main`.

`LEEME.md` no estorba, pero puedes no subirlo.

Después de publicar, verifica con el dominio real:

1. Que las fuentes se vean (titulares en IBM Plex Sans, cifras en Plex Mono). Si se ven en Arial, la carpeta `assets/fonts/` no subió.
2. Que el botón de WhatsApp abra el chat con el mensaje precargado.
3. Que el sitio cargue por `https://`. Si el hosting da certificado gratis (Let's Encrypt), actívalo.

## Editar el contenido

Todo el texto está en `index.html`, en español y en orden de lectura. Busca la sección por su `id`: `#inicio`, `#que-es`, `#servicios`, `#resultados`, `#como`, `#quien`, `#contacto`.

**Las cifras están en dos lugares y tienen que coincidir:** las cuatro tarjetas de arriba (`.cifras`) y la tabla de `#resultados`. Si cambias una, cambia la otra y revisa que el pie de fuente siga siendo cierto.

**Reglas de marca que el sitio ya cumple y conviene no romper:**

- Cinco colores. Agua manda, Grafito sostiene, Señal solo en cifras, viñetas y el botón de acción.
- Sin emoji y sin iconos. La viñeta es el guion Señal. Los cuatro ticks de la regla graduada, que en el sistema van en la esquina superior derecha de las piezas cuadradas, aquí no se usan: sobre una web se leen como menú hamburguesa.
- El eslogan "Sostenibilidad que se mide y se ejecuta" abre la página como antetítulo del héroe y la cierra en el pie, igual que la portada y la contraportada del portafolio.
- Sin degradados, sombras, transparencias ni animaciones de entrada. Solo transiciones de color de 120 ms.
- Titulares en caja de oración. Antetítulos y cifras en Plex Mono.
- El sello GPS de la foto de recorrido no se recorta: es la fuente de la foto.
- Toda cifra lleva su fuente visible y no se redondea hacia arriba.

## Cambiar las fotos

Las originales están en `Sobre-mi/Baremo Design System/assets/images/`, con sus pies en `pies-de-foto.md`. Las de esta carpeta ya están redimensionadas (900 px de ancho las del bloque de tres, 1280 px la ancha) y recomprimidas a calidad 82. Si metes una foto nueva sin redimensionar vas a subir de 2 MB por imagen y el sitio se va a sentir lento en celular.

Regla del sistema: las fotos **de trabajo** (firma, plano, recorrido, medición, verificación) son las únicas que pueden acompañar una sección que hable de resultados. Las de territorio sirven de contexto.

## Ver el sitio en local

Ábrelo con doble clic sobre `index.html`. Funciona, con una salvedad: Chrome bloquea la carga de fuentes desde `file://`, así que los textos se van a ver con la tipografía del sistema. Sobre el dominio publicado se ven bien.

## Lo que no tiene todavía

- Formulario de contacto. El contacto es por WhatsApp y correo, a propósito.
- Analítica. Si más adelante quieres saber cuánta gente entra, va un script en el `<head>`.
- Versión en inglés.
- Página de política de tratamiento de datos. Si en algún momento se agrega un formulario, en Colombia la Ley 1581 de 2012 la exige.

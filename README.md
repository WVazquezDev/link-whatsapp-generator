# LinkZapWV | Generador de enlaces de WhatsApp

Aplicacion web construida con **Astro** para crear enlaces directos de WhatsApp (`https://wa.me/...`) de forma rapida, con prefijo internacional, numero de telefono, mensaje opcional y codigo QR descargable.

## Tabla de contenido

- [Descripcion](#descripcion)
- [Funciones principales](#funciones-principales)
- [Tecnologias](#tecnologias)
- [Requisitos previos](#requisitos-previos)
- [Instalacion y ejecucion local](#instalacion-y-ejecucion-local)
- [Como usar la aplicacion](#como-usar-la-aplicacion)
- [Scripts disponibles](#scripts-disponibles)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Detalles tecnicos importantes](#detalles-tecnicos-importantes)
- [Personalizacion rapida](#personalizacion-rapida)
- [Autor](#autor)

## Descripcion

**LinkZapWV** ayuda a generar links listos para abrir chat en WhatsApp sin guardar informacion del usuario.

Caso de uso comun:

- Compartir un numero con mensaje predefinido para ventas, soporte o contacto.
- Evitar errores al escribir manualmente un enlace `wa.me`.
- Entregar tambien un QR para abrir el chat desde otro dispositivo.

## Funciones principales

- Seleccion de prefijo internacional por pais.
- Validacion de telefono (solo numeros, 10 digitos segun la logica actual).
- Mensaje opcional incluido en el enlace usando `encodeURIComponent`.
- Generacion de enlace de WhatsApp en formato `wa.me`.
- Copia del enlace al portapapeles con un clic.
- Generacion de codigo QR del enlace.
- Descarga del QR en formato PNG.
- Vista previa tipo chat para mostrar contacto y mensaje.

## Tecnologias

- [Astro 5](https://docs.astro.build/)
- [Tailwind CSS 4](https://tailwindcss.com/)
- JavaScript del lado del cliente
- [qrcode](https://www.npmjs.com/package/qrcode)
- [@fontsource-variable/onest](https://www.npmjs.com/package/@fontsource-variable/onest)

## Requisitos previos

- [Node.js](https://nodejs.org/) (LTS recomendado)
- [pnpm](https://pnpm.io/)

> Este proyecto usa `pnpm@10` (ver `packageManager` en `package.json`).

## Instalacion y ejecucion local

1. Clona el repositorio:

```bash
git clone https://github.com/WVazquezDev/link-whatsapp-generator.git
cd link-whatsapp-generator
```

2. Instala dependencias:

```bash
pnpm install
```

3. Inicia el servidor de desarrollo:

```bash
pnpm dev
```

4. Abre la app en tu navegador:

```text
http://localhost:4321
```

## Como usar la aplicacion

1. Selecciona un **prefijo internacional**.
2. Escribe el **numero de telefono** (10 digitos).
3. (Opcional) Escribe un **mensaje**.
4. Haz clic en **Generar enlace**.
5. Usa el boton **Copiar** para enviar el link.
6. (Opcional) Descarga el **QR** con el boton **Descargar**.

Ejemplo de enlace generado:

```text
https://wa.me/521234567890?text=Hola%2C%20quiero%20mas%20informacion
```

## Scripts disponibles

- `pnpm dev`: levanta el entorno de desarrollo.
- `pnpm build`: genera el build de produccion en `dist/`.
- `pnpm preview`: sirve localmente el build generado.
- `pnpm astro`: ejecuta comandos del CLI de Astro.

## Estructura del proyecto

```text
.
├── public/                        # Imagenes e iconos estaticos
├── src/
│   ├── components/
│   │   ├── Converter.astro        # UI y logica principal (formulario, link, QR)
│   │   ├── icons/                 # Componentes de iconos
│   │   └── layout/
│   │       ├── Navbar.astro       # Barra superior
│   │       └── Footer.astro       # Pie de pagina
│   ├── Layouts/
│   │   └── Layout.astro           # Estructura base del sitio
│   ├── pages/
│   │   └── index.astro            # Pagina principal
│   ├── styles/
│   │   └── global.css             # Import global de Tailwind
│   └── utils/
│       └── constants.js           # Lista de paises y prefijos
├── astro.config.mjs
├── package.json
└── README.md
```

## Detalles tecnicos importantes

- El boton **Generar enlace** se habilita cuando:
  - Hay un prefijo seleccionado.
  - El telefono tiene exactamente 10 digitos.
- El input de telefono elimina caracteres no numericos automaticamente.
- El mensaje se codifica con `encodeURIComponent`.
- El QR se genera en cliente y se muestra dentro de `#qrcode`.
- El boton de descarga toma la imagen QR renderizada y la guarda como `qr-512x512.png`.

## Personalizacion rapida

- Cambiar o ampliar prefijos:
  - Edita `src/utils/constants.js`.
- Ajustar validacion de telefono:
  - Edita la logica en `src/components/Converter.astro` (eventos de `input`/`change`).
- Cambiar estilos globales:
  - Edita `src/styles/global.css` y clases Tailwind en componentes.

## Autor

- GitHub: [@WVazquezDev](https://github.com/WVazquezDev)

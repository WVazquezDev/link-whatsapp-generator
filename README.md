# LinkZapWV - WhatsApp Link Generator

Aplicacion web para generar enlaces directos de WhatsApp (`wa.me`) con prefijo internacional, numero de telefono y mensaje opcional, sin guardar datos del usuario.

## Vista general

Este proyecto permite:
- Seleccionar prefijo internacional desde una lista de paises.
- Validar que el telefono tenga 10 digitos (segun la logica actual).
- Escribir un mensaje personalizado.
- Generar el enlace de WhatsApp listo para usar.
- Copiar el enlace al portapapeles con un clic.
- Ver una previsualizacion tipo chat dentro de la interfaz.

## Tecnologias

- [Astro 5](https://docs.astro.build/)
- [Tailwind CSS 4](https://tailwindcss.com/)
- JavaScript (cliente)
- Fuente `Onest Variable` via `@fontsource-variable/onest`

## Requisitos previos

- [Node.js](https://nodejs.org/) (version LTS recomendada)
- [pnpm](https://pnpm.io/) (el proyecto usa `pnpm@10`)

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

4. Abre en el navegador:

```text
http://localhost:4321
```

## Scripts disponibles

- `pnpm dev`: inicia el entorno de desarrollo.
- `pnpm build`: crea el build de produccion en `dist/`.
- `pnpm preview`: sirve localmente el build generado.
- `pnpm astro`: ejecuta comandos CLI de Astro.

## Como usar la aplicacion

1. Elige un prefijo internacional.
2. Escribe el numero de telefono.
3. (Opcional) Escribe un mensaje.
4. Haz clic en `Generar enlace`.
5. Copia el enlace generado y compartelo donde lo necesites.

Ejemplo de salida:

```text
https://wa.me/521234567890?text=Hola%20quiero%20mas%20informacion
```

## Estructura del proyecto

```text
.
├── public/                     # Iconos e imagenes estaticas
├── src/
│   ├── components/
│   │   ├── Converter.astro     # Formulario y logica principal
│   │   ├── icons/              # Iconos de la interfaz
│   │   └── layout/             # Navbar y Footer
│   ├── Layouts/
│   │   └── Layout.astro        # Estructura base de la pagina
│   ├── pages/
│   │   └── index.astro         # Ruta principal
│   ├── styles/
│   │   └── global.css          # Import de Tailwind
│   └── utils/
│       └── constants.js        # Lista de prefijos telefonicos
├── astro.config.mjs
├── package.json
└── README.md
```

## Notas para desarrollo

- La validacion actual del telefono exige 10 digitos para habilitar el boton de generar.
- El mensaje se codifica reemplazando espacios por `%20`.
- El listado de prefijos se mantiene en `src/utils/constants.js`.

## Autor

- GitHub: [@WVazquezDev](https://github.com/WVazquezDev)

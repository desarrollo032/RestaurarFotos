# [RestorePhotos.io](https://restorephotos.io/)

Este proyecto restaura fotos de caras antiguas usando IA. Mira el [video explicativo de 4 minutos](https://twitter.com/nutlope/status/1614794731396931585) para ver cómo construí esto o ver la [demostración de 15 segundos](https://twitter.com/nutlope/status/1612488923716136962).

[![Face Photo Restorer](./public/screenshot.png)](https://restorephotos.io/)

## How it works

Utiliza un modelo ML del Applied Research Center llamado [GFPGAN](https://github.com/TencentARC/GFPGAN) on [Replicate](https://replicate.com/) para restaurar fotos de caras. Esta aplicación le brinda la posibilidad de cargar cualquier foto, que la enviará a través de este modelo ML utilizando una ruta API Next.js y devolverá su foto restaurada.

## Running Locally

Nota: acabo de agregar autenticación, por lo que estos pasos no están completos a partir de ahora. Puedes clonar desde [this specific commit](https://github.com/Nutlope/restorePhotos/tree/1c5c8ac4f52a08f68a3091d3b21be8a65aef71f2).

### Cloning the repository the local machine.

```bash
git clone
```

### Creación de una cuenta en Replicate para obtener una clave API. 
1. Vaya a [Replicar](https://replicate.com/) para crear una cuenta. 
2. Haga clic en su foto de perfil en la esquina superior derecha y haga clic en "Tablero". 
3. Haga clic en "Cuenta" en la barra de navegación. Y, aquí puede encontrar su token de API, cópielo.
### Storing API key in .env file.

Cree un archivo en el directorio raíz del proyecto con env. Y almacene su clave API en él, como se muestra en el archivo .example.env.
Si también desea limitar la tasa, cree una cuenta en UpStash, cree una base de datos Redis y complete las dos variables de entorno en `.env` también. Si no desea limitar la velocidad, no es necesario que realice ningún cambio.

### Instalando las dependencias.

```bash
npm install
```

### Ejecutando la aplicación. 
Luego, ejecute la aplicación en la línea de comando y estará disponible en `http://localhost:3000`.

```bash
npm run dev
```

## One-Click Deploy

Deploy the example using [Vercel](https://vercel.com?utm_source=github&utm_medium=readme&utm_campaign=vercel-examples):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/Nutlope/restorePhotos&env=REPLICATE_API_KEY&project-name=face-photo-restorer&repo-name=restore-photos)

## Powered by

This example is powered by the following services:

- [Replicate](https://replicate.com) (AI API)
- [Upload](https://upload.io) (storage)
- [Vercel](https://vercel.com) (hosting, serverless functions, analytics)
- [Auth.js](https://authjs.dev/) + [Neon](https://neon.tech/) (auth + DB)
- [Upstash](https://upstash.com/) Redis (rate limiting)

# Museo Realidad Virtual de la FACSO | UNSJ

Este repositorio contiene una versión exportada de Unity en WebGL para ser desplegada en un servidor web. 

## 📂 Estructura del Sitio

    /FACSOWEBVR
    │── index.html       # Página principal
    │── Build/           # Archivos generados por Unity
    │── TemplateData/    # Recursos adicionales de Unity
    └── README.md        # Documentación

## 🚀 Servidor Web con Apache o Nginx
Si se desea desplegar en un servidor, seguir estos pasos:

1. Subir la carpeta `FACSOWEBVR` al servidor (puedes usar FTP, SCP, o un repositorio Git) previamente clonada desde éste repositorio.

2. Configura el servidor para servir archivos estáticos:

Asegúrate de que el servidor sirva correctamente los archivos HTML, JS, y WASM.

✅ Apache (opcional, si index.html no se carga por defecto)

- Edita o agrega en el archivo `.htaccess`:

```
DirectoryIndex index.html
```

✅ Nginx (ejemplo de configuración):
- Edita el archivo de configuración de Nginx:

```
server {
    listen 80;
    server_name tu-dominio.com;
    root /ruta/a/FACSOWEBVR;
    index index.html;
}
```

Verificar la carga de los archivos: 
- Asegúrate de que los archivos .wasm, .js y .data se sirvan correctamente.

Acceder a la URL pública del servidor y verificar que el todo cargue correctamente.

## ⚠️ Consideraciones para Producción

- Compresión: No se usa compresión en la build para evitar problemas con servidores que no permiten configurar cabeceras HTTP (como GitHub Pages). Si el servidor lo permite, puedes habilitar la compresión Gzip o Brotli para mejorar la carga del sitio.

- HTTPS: WebGL requiere HTTPS para funcionar correctamente en la mayoría de los navegadores.

- Archivos estáticos: Asegurarse de que el servidor esté configurado para servir correctamente los archivos .wasm, .js, y .data.
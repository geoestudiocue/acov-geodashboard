# GeoDashboard ACOV 2026

Dashboard estático de seguimiento cartográfico, desarrollado con Leaflet, Chart.js y JavaScript.

## Aviso sobre datos

**Antes de publicar:** confirmar autorización institucional para divulgar los datos ACOV. Los archivos `plan.geojson` y `ejecutado.geojson` contienen identificadores y geometrías cartográficas detalladas y se descargarán íntegramente en el dispositivo de cualquier visitante del sitio. GitHub Pages NO protege los datos con contraseña. Para distribución restringida, usar plataforma privada autorizada por la institución; un repositorio privado no convierte automáticamente a GitHub Pages en sitio privado.

## Archivos para GitHub Pages

- `index.html`: visor, filtros, gráficos y mapa.
- `plan.geojson`: muestra planificada.
- `ejecutado.geojson`: ejecución cartográfica.
- `.nojekyll`: indica a GitHub Pages que publique los archivos sin procesarlos con Jekyll.

## Publicación

1. Crear un repositorio en GitHub, por ejemplo `geodashboard-acov`.
2. Subir **los archivos sueltos**, no este ZIP ni una carpeta que los contenga. `index.html` debe quedar en la raíz.
3. Abrir **Settings → Pages → Build and deployment**.
4. Elegir **Deploy from a branch**, seleccionar `main` y `/(root)`, guardar.
5. La URL habitual es `https://USUARIO.github.io/geodashboard-acov/`. Esperar a que GitHub confirme el despliegue.
6. Probar filtros, mapa y exportación CSV desde una ventana privada y desde un celular con datos móviles.

No se necesitan Python, QGIS ni PostgreSQL para visitar la web. El navegador requiere internet para obtener Leaflet, Chart.js, fuentes y el mapa base OpenStreetMap.

## Prueba local

En la carpeta del proyecto, ejecutar `python -m http.server 8000` y abrir `http://localhost:8000`. No abrir directamente `index.html` mediante `file://`, pues usa `fetch()` para leer los GeoJSON.

## Nota técnica

El sitio es estático. Los datos no se actualizan automáticamente desde PostgreSQL: para publicar nuevos avances, exportar y reemplazar los dos GeoJSON, respetando su estructura y criterios de cálculo. Los mosaicos de OpenStreetMap dependen de su servicio externo y de su política de uso.

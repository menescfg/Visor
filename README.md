
# Preliminar SIG (Leaflet + GitHub Pages)

Estructura:
```
/data
  puntos.geojson
  zonas.geojson
/images
  Soyapango.png
/css
  style.css
index.html
```

## Pasos para publicar en GitHub Pages
1) Crea un repositorio en GitHub llamado `tesis-sig-preliminar`.
2) Sube **todo** el contenido de esta carpeta al repositorio.
3) En GitHub, ve a **Settings → Pages** y en "Build and deployment" selecciona **Deploy from a branch** y elige `main` y la carpeta `/root`.
4) Espera a que se despliegue. Podrás ver el mapa en:
   `https://<tu-usuario>.github.io/tesis-sig-preliminar/`

## Cómo reemplazar los datos
- Exporta desde QGIS tus capas a **GeoJSON** y substituye `data/puntos.geojson` y `data/zonas.geojson`.
- Puedes agregar más archivos GeoJSON y cargar más `fetch()` en `index.html`.
- Para mostrar la imagen como overlay georreferenciado, ajusta las coordenadas de las esquinas en:
  ```js
  const overlay = L.imageOverlay('images/Soyapango.png', [[lat1, lon1], [lat2, lon2]]);
  overlay.addTo(map);
  ```

## Privacidad (preliminar)
- Este demo es **público** por defecto. Para no exponer coordenadas sensibles:
  - Usa geometrías **simplificadas** para el repositorio público.
  - Mantén los datos sensibles en otro repo **privado** si deseas compartirlos solo con personas con cuenta de GitHub.

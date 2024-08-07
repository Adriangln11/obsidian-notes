---
id: rendering
aliases:
  - Tipos de renderizado
tags:
  - frontend
  - architecture
  - seo
---

# Tipos de renderizado (aplicaciones web)

---

## Client Side Rendering (CSR)

Algunos ejemplos de CSR son el uso de frameworks como React o Angular, ya que todo el Javascript que se descarga es ejecutado directamente en el navegador y esto es lo que le da la funcionalidad.

- El navegador descarga un archivo HTML junto con sus respectivos archivos JS y CSS.
- El contenido del archivo JS se ejecuta en el navegador una vez que se descarga, esto construye las interfaces que sean dinámicas.

### Ventajas

1. La carga al servidor es menor.
2. Mejor UX.
3. Interacciones del usuario más rapidas.

### Desventajas

1. El SEO no es óptimo.
2. Los tiempos de carga inicial suelen ser mayores.

---

## Server Side Rendering (SSR)

Los ejemplos más conocidos de la aplicación de SSR son frameworks como Nextjs, Nuxtjs, o PHP.

- El HTML que se envía al navegador es creado directamente desde el navegador, a diferencia del CSR en donde el HTML enviado es un archivo estático que se sube al servidor.
- Ya que los archivos son creados en el servidor también pueden ser ejecutados en el mismo, por lo que en el navegador no hay necesidad de ejecutar demasiado Javascript.

### Ventajas

1. Mejora el SEO del sitio.
2. Mejores tiempos de carga mas rapido.
3. Mejor para sitios estáticos.

### Desventajas

1. El contenido dinámico es poco o nulo.
2. Sí hay contenido dinámico el tiempo de carga puede ser alto.

---

## Server Site Generation (SSG)

Genera archivos HTML estáticos para todas las páginas de la aplicación en el momento de la contrucción del sitio en lugar de hacerlo dinámicamente o en el cliente en tiempo de ejecución.

### Ventajas

1. No se requiere procesamiento adicional del cliente.
2. Mejor SEO, facil de indexar.
3. Mejor seguridad cuando no hay capa de servidor dinámico.
4. Facil de escalar con CDN's.

### Desventajas

1. No es ideal para contenido que cambia frecuentemente.
2. El tiempo de contrucción puede ser alto.

---

## Hydratation

La hidratación de un sitio hace referencia a la aplicación de los dos tipos de renderizado anteriormente mencionados (CSR, SSR). Nextjs es un framework que puede implementar esta hidratación.

- Los archivos HTML son renderizados en el servidor.
- El Javascript es cargado en el navegador.

### Ventajas

1. Combina lo mejor del SSR y CSR.
2. Tiempos de carga más rapidos sin la carga al servidor.

### Desventajas

1. Menos flexible con contenidos dinámicos.

---

## Prerenderizado

Este tipo de renderizado se usa para generar contenido estático solo en algunas rutas al mismo tiempo que se contruye la aplicación.

### Ventajas

1. Buen SEO.
2. Tiempos de carga rapidos.
3. Poca carga en el servidor.

### Desventajas

1. Menos flexible para contenido dinámico.

---

## Incremental Static Regeneration (ISR)

Combina la prerenderización y regeneración de páginas estáticas en tiempo real en el momento que se accede a ellas.

### Ventajas

1. Permite contenido estático con actualizaciones dinámicas.
2. Buen SEO y rendimiento.

### Desventajas

1. Requiere configuración y es comlpejo de implementar.

---

## Edge-Side Rendering (ESR)

Utiliza CDN para proveer el contenido y en estos intermediarios se renderiza el contenido.

### Ventajas

1. Mejora los tiempos de respuesta.
2. Distribuye mejor la carga del contenido.

### Desventajas

1. Requiere configuración y una buena infraestructura.

---

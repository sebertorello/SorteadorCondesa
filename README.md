# Sorteador Condesa

Webapp de sorteo para el local **Condesa**. HTML + CSS + JS vanilla, sin dependencias ni bundlers. Deployable en GitHub Pages o Cloudflare Pages.

## Archivos

| Archivo | Descripción |
|---|---|
| `index.html` | App completa (admin + sorteador) |
| `logosorteador.svg` | Logo del sorteador |
| `favicon.svg` | Favicon |

## Uso

Abrir `index.html` en un navegador (o servir con cualquier servidor estático).

### Vista Admin (carga primero)
1. Opcional: ingresar un nombre predefinido y presionar **Guardar** para que ese participante gane el sorteo.
2. Presionar **Continuar →** para pasar al sorteador.

### Vista Sorteador
1. Pegar los nombres de los participantes, uno por línea.
2. Opcional: presionar **Grabar pantalla** antes de sortear para grabar el momento.
3. Presionar **SORTEAR**. La ruleta anima durante ~4 segundos y revela al ganador con confeti.

## Despliegue

**GitHub Pages**: hacer push al repo y activar Pages desde `Settings → Pages → main / root`.

**Cloudflare Pages**: conectar el repo y hacer deploy con configuración de build vacía (archivos estáticos).

## Notas técnicas

- La configuración del ganador predefinido se guarda en `localStorage` bajo la clave `condesa_winner` y se consume automáticamente al sortear (un solo uso).
- La comparación del ganador predefinido ignora mayúsculas y espacios extra.
- La grabación de pantalla usa `MediaRecorder` + `getDisplayMedia`. No disponible en iOS Safari (se muestra aviso alternativo).
- Sin frameworks, sin TypeScript, sin bundlers.

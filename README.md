# OficinaPro Leads

Lista diaria de propiedades en venta por **DUEÑO DIRECTO** en la Costa Atlántica argentina.
Generada automáticamente todas las noches a las 23:01.

## URL para consumir desde el portal

```
https://raw.githubusercontent.com/matiasmelia/oficinapro-leads/main/propiedades.json
```

Ejemplo en JavaScript:
```javascript
const r = await fetch('https://raw.githubusercontent.com/matiasmelia/oficinapro-leads/main/propiedades.json');
const data = await r.json();
console.log(data.meta);          // { generated_at, fecha, total, cambios_precio, nuevas_vs_ayer, ... }
console.log(data.propiedades);   // Array de propiedades
```

## Estructura del JSON

```json
{
  "meta": {
    "generated_at": "2026-05-22T23:01:00",
    "fecha": "2026-05-22",
    "total": 914,
    "cambios_precio": 12,
    "nuevas_vs_ayer": 45,
    "fuentes": ["Argenprop", "MercadoLibre", "Zonaprop"],
    "zonas": ["Partido de la Costa", "Pinamar y zona", "Villa Gesell y zona"]
  },
  "propiedades": [
    {
      "link": "https://www.zonaprop.com.ar/propiedades/...",
      "titulo": "Casa en Pinamar Norte 3 ambientes",
      "precio": "USD 325.000",
      "precio_monto": 325000,
      "precio_moneda": "USD",
      "ciudad": "Pinamar",
      "zona": "Pinamar y zona",
      "fuente": "Zonaprop",
      "tipo": "Casa",
      "ubicacion": "Pinamar Norte, Pinamar",
      "antiguedad": "Publicado hoy",
      "publisher": "Dueño Directo",
      "es_nuevo_vs_ayer": true,
      "cambio_precio": null
    },
    {
      "...": "...",
      "cambio_precio": {
        "precio_anterior_str": "USD 343.000",
        "precio_anterior_monto": 343000,
        "precio_anterior_moneda": "USD",
        "delta": -18000,
        "pct": -5.25,
        "subio": false
      }
    }
  ]
}
```

## Clave única

El campo `link` es la **clave única** para cada propiedad. El portal debe
matchear por este campo cuando hace merge con su tabla local de leads.

## Frecuencia de actualización

- 1 commit por día (~23:01 hora Argentina)
- Si una propiedad desaparece de los portales (vendida o despublicada), deja
  de figurar en el JSON al día siguiente.

## Cobertura

**22 ciudades:** Pinamar, Valeria del Mar, Cariló, Ostende, Montecarlo, Mar de
Ostende, Costa Esmeralda, Villa Gesell, Mar de las Pampas, Mar Azul, Las
Gaviotas, San Bernardo, Mar de Ajó, Santa Teresita, San Clemente del Tuyú,
La Lucila del Mar, Las Toninas, Costa del Este, Aguas Verdes, Costa Azul,
Costa Chica, Mar del Tuyú.

**3 portales:** Zonaprop, Argenprop, MercadoLibre.

## Último update

- **Fecha:** 2026-05-23
- **Total propiedades:** 914
- **Con cambio de precio:** 0
- **Nuevas vs ayer:** 914

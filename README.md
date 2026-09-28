# Índice de amortización del termostato inteligente por CCAA (2026)

En cuántos años se paga solo un termostato inteligente en cada comunidad autónoma de
España, según el clima y el tipo de calefacción. Una sola fórmula, aplicada igual a las 17
comunidades, con datos públicos.

El CSV de este repositorio es el mismo archivo publicado en
<https://hogarconectado.co/assets/data/indice-amortizacion-ccaa-2026.csv>.

- **Página canónica (método, tabla y límites):** <https://hogarconectado.co/guias/indice-amortizacion-hogar-inteligente-ccaa-2026>
- **Versión:** 1.0 · **Publicado:** 2026-07-11 · **Última revisión:** 2026-07-16
- **Licencia:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.es) — úsalo, citándolo.

## Lo primero, para que nadie se lleve una sorpresa

**El dataset tiene 17 filas pero solo 4 valores distintos.** El consumo de calefacción de
referencia lo publica el IDAE (SPAHOUSEC) **por zona climática, no por comunidad autónoma**.
A cada comunidad se le asigna la zona de invierno del CTE de su capital, de modo que todas
las comunidades que comparten zona comparten cifra:

| Zona de invierno (CTE) | Comunidades | Calefacción de referencia |
|---|---|---|
| D (muy fría) | 7 | 8.600 kWh/año |
| C | 5 | 7.400 kWh/año |
| B | 4 | 6.200 kWh/año |
| A (muy suave) | 1 (Canarias) | 2.000 kWh/año |

Es decir: Madrid, Zaragoza, Valladolid, Logroño, Oviedo, Pamplona y Vitoria-Gasteiz tienen
números idénticos porque están en la misma zona climática, no porque se hayan medido por
separado. **Si citas este índice, dilo así.** Presentarlo como "amortización comunidad por
comunidad" sin esta advertencia da a entender una granularidad que el dato no tiene.

## La fórmula

```
ahorro (kWh/año)   = calefacción de referencia x 12 %
ahorro (€/año)     = ahorro kWh x precio de la energía
amortización (años) = 150 € (precio del termostato) / ahorro €/año
```

Precios usados: **gas natural 0,09 €/kWh** y **calefacción eléctrica 0,16 €/kWh**.
El 12 % de ahorro es deliberadamente conservador: los estudios publicados (IDAE, ECODES)
sitúan el rango real entre el 8 % y el 23 %.

## Columnas

| Columna | Unidad | Significado |
|---|---|---|
| `comunidad` | — | Comunidad autónoma |
| `capital` | — | Capital cuya zona climática se asigna a la comunidad |
| `zona_invierno_cte` | A–D | Zona de invierno del CTE DB-HE de esa capital |
| `calefaccion_kwh_ano` | kWh | Consumo de calefacción de referencia de esa zona |
| `ahorro_kwh_ano` | kWh | Ahorro estimado (12 % del consumo) |
| `ahorro_eur_ano_gas` | € | Ahorro anual con gas natural a 0,09 €/kWh |
| `amortizacion_anos_gas` | años | 150 € ÷ ahorro con gas |
| `ahorro_eur_ano_electrico` | € | Ahorro anual con calefacción eléctrica a 0,16 €/kWh |
| `amortizacion_anos_electrico` | años | 150 € ÷ ahorro eléctrico |

## Fuentes

- **Consumo de calefacción por zona climática:** IDAE, estudio SPAHOUSEC.
- **Zona de invierno por capital:** CTE DB-HE (Código Técnico de la Edificación).
- **Precios de la energía:** precios públicos de referencia para gas natural y electricidad.

## Límites — léelos antes de citarlo

- **Granularidad por zona climática, no por comunidad** (ver arriba). Es el límite más
  importante.
- **Es una estimación, no una medición.** Nadie instaló 17 termostatos para producir estas
  cifras: es un cálculo sobre consumos de referencia publicados.
- **El 12 % es un supuesto conservador.** Tu ahorro real depende sobre todo de cómo
  gestionabas la calefacción antes: si ya eras disciplinado, ahorrarás menos; si la dejabas
  encendida todo el día, bastante más.
- **Amortización simple.** No incluye inflación de la energía ni descuento financiero.
- **Precio del termostato fijado en 150 €.** Hay modelos por menos y sistemas multizona muy
  por encima; escala la amortización proporcionalmente.
- **Una vivienda tipo por zona.** No distingue superficie, aislamiento ni número de
  ocupantes.

## Cómo citarlo

> de Madrazo, B. (2026). *Índice de amortización del termostato inteligente por comunidad
> autónoma (2026)* (Versión 1.0) [Conjunto de datos]. Hogar Conectado.
> https://hogarconectado.co/guias/indice-amortizacion-hogar-inteligente-ccaa-2026

```bibtex
@dataset{demadrazo2026ccaa,
  author    = {de Madrazo, Bruno},
  title     = {Índice de amortización del termostato inteligente por CCAA 2026},
  year      = {2026},
  version   = {1.0},
  publisher = {Hogar Conectado},
  url       = {https://hogarconectado.co/guias/indice-amortizacion-hogar-inteligente-ccaa-2026},
  note      = {CSV: https://hogarconectado.co/assets/data/indice-amortizacion-ccaa-2026.csv. Licencia CC BY 4.0}
}
```

## Correcciones

Los errores detectados en este dataset o en sus páginas se registran públicamente en
<https://hogarconectado.co/correcciones>.

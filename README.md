# Despacho Económico en el Mercado Eléctrico Colombiano

Este proyecto simula de forma simplificada el proceso de **despacho económico diario** que realiza el Centro Nacional de Despacho (CND) en el mercado eléctrico colombiano, gestionado por **XM**. Usando datos públicos, se reproduce el análisis para determinar **qué plantas generadoras entrarían a operar** en un día específico, en función de sus precios ofertados y de la demanda proyectada.

El modelo busca aproximarse al principio real del sistema: **satisfacer la demanda al menor costo posible**, respetando restricciones técnicas y características de las plantas.

---

## Objetivo

Automatizar el proceso interno de despacho económico utilizando:
> - Precios horarios del mercado
> - Ofertas de generación por planta
> - Predicción de la demanda horaria
Con esta información, se simula qué plantas serían despachadas hora a hora, priorizando las de menor costo marginal.

---

## Lógica del modelo

1. **Carga de datos** desde archivos públicos de XM.
2. **Normalización** de nombres de plantas (ej. plantas con mismo precio y nombre distinto como `x1`, `x2` se agrupan).
3. **Filtrado** de ofertas no relevantes (precios artificialmente bajos o combinaciones inválidas).
4. Para cada hora:
   - Se ordenan plantas por precio
   - Se asigna generación hasta cubrir la demanda
5. Se obtienen:
   - Plantas despachadas
   - Energía generada por planta por hora
   - Costo total del despacho

---

## Resultados esperados

- Visualización del despacho por hora (gráfico de barras apiladas)
- Análisis del costo total de operación
- Identificación de plantas claves en la operación diaria

---

## Observaciones clave

Durante el análisis se identificaron aspectos importantes para mejorar la calidad del modelo:

- **Unificación de plantas** con nombres distintos pero mismo precio
- **Normalización de nombres combinados o mal escritos**
- **Filtrado de plantas que no participan realmente**, aunque tengan precios bajos
- **Plantas que no entregan toda su disponibilidad**, lo que refleja restricciones técnicas no visibles en los datos públicos

---

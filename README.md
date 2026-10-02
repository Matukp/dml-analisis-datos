# DML aplicado a análisis de datos

Práctica del **Módulo 1 – Unidad 3** del curso *Data Science II: Machine Learning para la Ciencia de Datos* (Coderhouse).

Reproduce el esquema propuesto en la unidad: usar las sentencias DML (`INSERT`, `UPDATE`, `DELETE`, `SELECT`) para transformar datos crudos en un dataset listo para Machine Learning, integrando SQL con Python.

## Contenido

| Archivo | Descripción |
|---|---|
| `dml_practica.ipynb` | Notebook ejecutado, con resultados visibles |
| `requirements.txt` | Dependencias |

## Pasos del notebook

1. **Preparación:** imports, semilla fija y base SQLite `features.db`.
2. **INSERT masivo:** tabla `features` con 50.000 registros simulados (incluye nulos y outliers a propósito) cargados con `executemany`.
3. **SELECT exploratorio con pandas:** conteo de nulos y tasa de positivos por categoría.
4. **UPDATE:** capeo de outliers de `feature1` al percentil 99 y nueva columna `feature1_scaled` (normalizada por el máximo).
5. **DELETE:** eliminación de filas sin `label` o sin ninguna feature.
6. **SELECT optimizado:** tiempos de una agregación sin índice vs. con índice cubriente (`EXPLAIN QUERY PLAN`).
7. **SQLAlchemy:** inserción de un batch con parámetros y guardado del dataset final con `to_sql`.

## Cómo ejecutarlo

```bash
pip install -r requirements.txt
jupyter notebook dml_practica.ipynb
```

La base `features.db` se genera al ejecutar el notebook (no se versiona).

---
Autor: Matías Rodríguez

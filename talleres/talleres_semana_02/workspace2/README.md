
# Taller Semana 2.2 — Análisis de Sensores IoT

## Qué vas a hacer (en 15 segundos)

Vas a procesar 1440 lecturas de 5 sensores agrícolas (24 horas de datos) para:

1. Agrupar lecturas por sensor usando diccionarios
2. Calcular estadísticas (promedio, máximos, mínimos)
3. Detectar periodos críticos (temperatura > 30°C por >1 hora)
4. Exportar resumen a CSV

## Dónde vas a trabajar

Todo el trabajo es en esta carpeta:

`talleres/taller_semana_02/workspace2/`

## Pasos (hazlos en orden)

### 1. Abre el archivo base

```bash
cd talleres/taller_semana_02/workspace2
```

Debes ver el código en el archivo `analisis_sensores.py`

### 2. Completa las 4 funciones

Busca los comentarios `# TODO:` y completa:

* `agrupar_por_sensor(lecturas)` → Diccionario {sensor_id: [lecturas]}
* `calcular_estadisticas(lecturas_sensor)` → Estadísticas por sensor
* `detectar_periodos_criticos(...)` → Lista de alertas
* `exportar_resumen(...)` → Escribe CSV con resultados

### 3. Ejecuta tu solución

```bash
python analisis_sensores.py
```

Deberías ver:

* Progreso por pasos [1/5] ... [5/5]
* Resumen por sensor
* Alertas detectadas (si hay)
* Archivo `resumen_sensores.csv` generado

### 4. Valida con el checker

```bash
python check_02.py
```

Si todo está bien, verás: `✓ APROBADO: 4/4 pruebas exitosas`

### 5. Revisa el archivo generado

```bash
cat resumen_sensores.csv
```

### 6. Haz commit

```bash
git add talleres/taller_semana_02/workspace2/analisis_sensores.py
git add talleres/taller_semana_02/workspace2/resumen_sensores.csv
git commit -m "feat: completar taller 02.2 análisis de sensores IoT"
git push
```

## Criterios de éxito (DoD)

* [x] `check_02.py` pasa sin errores (4/4 pruebas)
* [x] Se genera `resumen_sensores.csv` con 5 filas (una por sensor)
* [x] El programa imprime alertas si detecta periodos críticos
* [x] Al menos 1 commit con tu código en GitHub

## Conceptos clave practicados

* Diccionarios anidados (agrupación de datos)
* List comprehensions (extracción eficiente)
* Agregaciones (sum, max, min, mean)
* Escritura de CSV con `csv.DictWriter`
* Lógica de ventanas temporales

## Si tienes errores

**"KeyError":** Verifica que estés usando las claves correctas del CSV
**"TypeError":** Recuerda convertir strings a float/int antes de calcular
**CSV vacío:** Asegúrate de llamar `writeheader()` antes de `writerow()`
**Validador falla en estadísticas:** Verifica que `horas_luz` cuente lecturas con `luz_lux > 5000`

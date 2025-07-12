# Diagrama de flujo ampliado para draw.io

## INICIO

⬇️  
**main()**
- Inicializa arreglos: zonas[20], numZonas, reportes, etc.
- Ciclo principal: do { ... } while (opc != 8)

⬇️  
**menu()**
- Muestra menú principal y lee opción del usuario.

⬇️  
**switch(opc):**

---

### Caso 1: Crear zonas de monitoreo

⬇️
**crearZonasMonitoreo()**
- Solicita datos de zonas (nombre, ubicación, etc).
- Inicializa datos de contaminantes y factores climáticos.
- Guarda zonas en archivo con **guardarZonas()**
- Muestra mensaje de éxito.

---

### Caso 2: Mostrar zonas de monitoreo

⬇️
**cargarZonas(zonas, &numZonas)**
- Lee zonas desde archivo.
- Si éxito:
    - **mostrarZonas(zonas, numZonas)**
        - Muestra lista de zonas y sus datos históricos (contaminantes y factores climáticos).
- Si error: muestra mensaje.

---

### Caso 3: Generar predicción

⬇️
**cargarZonas(zonas, &numZonas)**
- Seleccionar zona por ID.
- Si zona y reporte actual existen:
    - **generarPrediccion(&zona, 1)**
        - Calcula valores predichos usando promedios y ponderaciones (**promedio()**, **promedioPonderado()**).
        - Muestra predicciones y mensajes de alerta según umbrales.
- Si error: muestra mensaje.

---

### Caso 4: Generar alertas

⬇️
**cargarZonas(zonas, &numZonas)**
- Seleccionar zona por ID.
- Si zona y reporte actual existen:
    - **generarAlertas(&zona, 1)**
        - Verifica si contaminantes actuales superan umbrales.
        - Muestra mensajes de alerta y recomendaciones en pantalla.
- Si error: muestra mensaje.

---

### Caso 5: Generar recomendaciones

⬇️
**cargarZonas(zonas, &numZonas)**
- Seleccionar zona por ID.
- Si zona y reporte actual existen:
    - **generarRecomendaciones(&zona, 1)**
        - Analiza datos históricos y actuales.
        - Sugiere recomendaciones en pantalla (reducir actividades, usar mascarillas, evacuar, etc).
- Si error: muestra mensaje.

---

### Caso 6: Exportar datos

⬇️
**cargarZonas(zonas, &numZonas)**
- Seleccionar zona por ID.
- Si zona y reporte actual existen:
    - **exportarDatos(&zona, 1)**
        - Exporta datos actuales e históricos a archivo.
        - Incluye recomendaciones y alertas en archivo.
- Si error: muestra mensaje.

---

### Caso 7: Ingresar reporte actual

⬇️
**cargarZonas(zonas, &numZonas)**
- Seleccionar zona por ID.
- Si zona existe:
    - **ingresarDatosActuales(&zona, 1)**
        - Solicita al usuario datos actuales (contaminantes, clima).
        - Actualiza datos actuales y mueve históricos.
    - **guardarZonas(zonas, numZonas)**
    - Muestra mensaje de éxito.
- Si error: muestra mensaje.

---

### Caso 8: Salir

⬇️
Muestra mensaje de salida y termina el programa.

## FIN

---

## Funciones principales (para draw.io como subprocesos):

- **leerCadena()**: Lee cadenas desde entrada.
- **obtenerFechaHora()**: Obtiene fecha y hora actual.
- **promedio(), promedioPonderado()**: Calculan promedios (usados en predicción).
- **agregarReporte()**: Agrega datos actuales al histórico.
- **pedirFlotanteValido()**: Valida entrada de datos numéricos.

---

## Sugerencia para Draw.io

- Para cada caso del menú, usa un rectángulo de proceso.
- Para cada función llamada (subproceso), crea un bloque aparte conectado por flechas.
- Usa rombos para decisiones: "¿Se cargaron las zonas?", "¿La zona existe?", "¿Hay datos actuales?", etc.
- Usa notas o cuadros laterales para describir brevemente cada función (como en el resumen).

---

Este diagrama de flujo puede copiarse y adaptarse fácilmente en draw.io, añadiendo conectores, decisiones y subprocesos según la estructura del código.

# Uso de IA — Portafolio U1

## 1. Uso de IA heredado del proyecto original (sin completar por el autor anterior)
El archivo `USO_IA_sin_completar.md` (conservado en esta carpeta) y el propio
`informe_final.docx` indican que parte de la redacción del informe se apoyó
en un asistente de IA, pero **no se registró qué fragmentos se generaron ni
cómo se verificaron**. No fue posible reconstruir esa información porque no
existe evidencia adicional (ni historial, ni notas del autor). Se declara
esta limitación explícitamente en el README (sección "Limitaciones") en
lugar de inventar una justificación retroactiva.

## 2. Uso de IA en esta unidad (auditoría, reorganización y documentación)
- **Herramienta:** Claude (Anthropic).
- **Propósito:** apoyar la auditoría del proyecto heredado, la reorganización
  de archivos en carpetas por rol (datos de origen / procesos / resultados /
  documentación), la verificación del cálculo de área y unidades de la
  planilla de ensayo, y la redacción del `README.md` y de esta declaración.
- **Salida utilizada:** texto del `README.md`, de esta declaración, y la
  estructura de carpetas propuesta; también la verificación numérica del
  área de la probeta (π/4·D²) y del orden de magnitud de la tensión máxima.
- **Cómo se verificó:**
  - El cálculo de área (17 671,46 mm² para D = 150 mm) se recalculó de forma
    independiente y coincide con el valor usado en la planilla heredada.
  - El supuesto de que la carga está en kN se contrastó comparando el
    resultado de tensión máxima (≈ 25,46 MPa) con el rango típico de
    resistencia del hormigón estructural (20–40 MPa); la alternativa
    (carga en N) da un resultado físicamente incoherente.
  - El contenido de los archivos heredados (xlsx, docx, notas, imagen) se
    inspeccionó directamente antes de redactar el README, en vez de asumir
    su contenido.
- **Decisión final:** se aceptó el texto propuesto para el README y esta
  declaración, ajustando los datos personales (nombre, repositorio, commit)
  antes de la entrega. El supuesto de unidades queda marcado como pendiente
  de confirmar, no como un hecho verificado con el autor original.

> *(Estudiante: revise y ajuste este archivo para que refleje fielmente
> cómo usó la IA en su propio trabajo antes de entregar.)*

# Portafolio U1 — Ensayo de compresión de hormigón

## Propósito
Procesar los datos de un ensayo de compresión sobre una probeta cilíndrica de
hormigón (heredados de un integrante anterior) para obtener la curva
esfuerzo–desplazamiento y la resistencia máxima, dejando el flujo de trabajo
documentado y reproducible por un tercero.

## Estructura del proyecto
```
01_datos_origen/        Datos crudos del ensayo, sin modificar (evidencia original)
02_procesos_analisis/   Planilla con los cálculos (carga -> tensión)
03_resultados_figuras/  Gráfico final exportado
04_documentacion/       Informe heredado, este README y la declaración de uso de IA
```
Los archivos originales se conservaron sin editar su contenido; solo se
reubicaron en carpetas según su rol en el flujo (dato de origen, análisis,
resultado o documentación).

## Entradas
- `01_datos_origen/ensayo_hormigon.xlsx`: datos crudos del ensayo (columnas
  `tiempo`, `carga`, `desplazamiento`) y las dimensiones de la probeta
  (diámetro D = 150 mm, altura H = 300 mm), anotadas junto a los datos.
- `01_datos_origen/notas.txt`: notas originales del integrante anterior.
  Señalan que debía usarse el archivo "FINAL_v2" y que faltaba revisar
  las unidades — ambas observaciones se auditaron en este portafolio.

## Procedimiento
1. La planilla `02_procesos_analisis/ensayo_hormigon_FINAL_v2.xlsx` toma la
   columna `P` (carga) y calcula la tensión con la fórmula:
   `sigma = P * 1000 / 17671.46` (columna `sigma`, en MPa).
2. El valor `17671.46` corresponde al área de la sección circular de la
   probeta: `A = π/4 · D²` con `D = 150 mm` → `A = 17 671,46 mm²`. Este
   cálculo no estaba documentado en el archivo heredado; se verificó y se
   deja registrado aquí para que sea trazable.
3. La tensión máxima se obtiene con `fmax = MAX(columna sigma)`.
4. El gráfico `03_resultados_figuras/grafico_final.png` (esfuerzo vs.
   desplazamiento) se generó a partir de estos mismos datos.

## Salidas
- Curva esfuerzo–desplazamiento (`03_resultados_figuras/grafico_final.png`).
- Tensión máxima calculada ≈ 25,46 MPa (ver `02_procesos_analisis/ensayo_hormigon_FINAL_v2.xlsx`, celda `fmax`).
- Informe heredado (`04_documentacion/informe_final.docx`).

## Herramientas utilizadas
Microsoft/LibreOffice Excel (planilla de cálculo), Git/GitHub (control de
versiones), un asistente de IA para reorganizar y documentar el proyecto
(ver `04_documentacion/USO_IA.md`).

## Unidades y supuestos
- Dimensiones de la probeta: D = 150 mm, H = 300 mm.
- **Supuesto crítico (no confirmado con el autor original):** la carga `P`
  se asume en **kN**. Con ese supuesto, la tensión máxima resulta ≈ 25,46 MPa,
  valor coherente con la resistencia típica de un hormigón estructural
  (≈ 20–40 MPa). Si `P` estuviera en N, el resultado sería ≈ 0,0255 MPa,
  fisicamente incoherente para hormigón. Este supuesto se adopta como la
  interpretación más plausible, pero queda declarado como pendiente de
  confirmar con la fuente original de los datos.
- El área de la sección (17 671,46 mm²) se calculó a partir de D = 150 mm
  (ver "Procedimiento", paso 2).
- El gráfico no traía unidades en los ejes; se recomienda regenerarlo
  indicando "Esfuerzo (MPa)" y "Desplazamiento (mm)" en una próxima
  iteración (ver limitaciones).

## Limitaciones
- No se pudo confirmar con el autor original la unidad real de la columna
  `carga`; se trabajó bajo el supuesto declarado arriba.
- El archivo `ensayo_hormigon_FINAL_v2.xlsx` fue heredado con ese nombre;
  se conservó tal cual por trazabilidad, aunque el sufijo "FINAL_v2" es
  ambiguo (no indica qué diferencia a la v1 de la v2, ni por qué es "final").
- El gráfico final no indica unidades en los ejes ni referencia el archivo
  y la versión de datos que lo generaron.
- Parte de la redacción del informe heredado se apoyó en un asistente de IA
  sin registrar qué fragmentos se usaron (ver `USO_IA.md` para el detalle
  de esta unidad).

## Cómo continuar este trabajo
1. Confirmar la unidad real de la columna `carga` con el integrante original
   o con el instrumento de ensayo utilizado.
2. Regenerar el gráfico con unidades explícitas en los ejes.
3. Si se agregan nuevos ensayos, crear una nueva carpeta en
   `01_datos_origen/` (no sobrescribir los datos crudos existentes) y
   documentar el cambio en un nuevo commit.

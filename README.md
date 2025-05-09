# Modelado de Potencial Solar - San Pedro, Costa Rica (2023)

## Descripción
Estimación de la generación de energía ideal de un panel solar fotovoltaico (Canadian Solar 430W, tilt 10°, azimuth 288º) en San Pedro, Costa Rica (Lat: 9.93°, Lon: -84.04°), usando datos horarios de 2023 y Python. 

## Objetivo Principal
Estimar la potencia horaria teórica del panel como base para futuros análisis de rendimiento o detección de anomalías.

## Fuente de Datos

* **Datos Meteorológicos:** Se utilizaron datos horarios para el año 2023 obtenidos del National Solar Radiation Database (NSRDB) de NREL para la ubicación especificada (Lat: 9.93°, Lon: -84.04°).
* **Archivo:** `977348_9.93_-84.06_2023.csv` (incluido en la raíz de este repositorio).
    * *Nota:* Las marcas de tiempo en este archivo CSV están originalmente en **UTC**. El código (`implementación_del_modelo.ipynb`) **convierte** estas marcas de tiempo a la zona horaria local de Costa Rica (`America/Costa_Rica`, UTC-6) antes del análisis.

## Metodología
1.  Cálculo de posición solar.
2.  Estimación de irradiancia en el plano del panel (POA).
3.  Cálculo de temperatura de celda.
4.  Aplicación del Modelo Single-Diode (`pvlib`) para obtener potencia horaria estimada (Pmp).

## Herramientas Clave
* Python 3.9+
* pvlib-python
* pandas
* numpy
* plotly (para gráficos en notebook)

*(Ver `requirements.txt` para detalles)*

## Cómo Ejecutar
1.  Clonar el repositorio.
2.  (Opcional) Crear y activar un entorno virtual.
3.  Instalar dependencias: `pip install -r requirements.txt`
4.  Ejecutar el notebook `implementación_del_modelo.ipynb` con Jupyter.

   
## Resultados (Simulación Ideal)
* Producción Anual Estimada: ~628.09 kWh
* Factor de Capacidad Estimado: ~16.6%


## Limitaciones
Simulación idealizada. No considera pérdidas reales (suciedad, sombras, inversor, degradación, etc.).

IELE756 — Proyecto Final: One Anomaly, Defended
Equipo 19 — Borja Landerretche y Martín Crisóstomo Curso: Preparación y Análisis de Datos (IELE756) Profesor: Leo Ferres, PhD Fecha: 22 de mayo de 2026


________________


TL;DR
Anomalía defendida: la comuna de San Pedro (Provincia de Melipilla, Región Metropolitana) presenta un residuo de Pearson de +5.11 (z ≈ +6.30) en un modelo Binomial Negativo de notificaciones ENO ajustado sobre las 51 comunas de la RM. El modelo predice una tasa de 107.7 / 10.000 habitantes, pero la observada es de 609.2 / 10.000 — casi 6 veces más alta de lo esperado dado su perfil demográfico. Es la comuna más extrema de la distribución regional de residuos, por un margen amplio.
Comunas asignadas al equipo
* Conchalí (13104)
* La Cisterna (13109)
* Quinta Normal (13126)


Comuna focal de la anomalía: San Pedro (13505).
La anomalía en una oración
San Pedro notifica casos ENO a una tasa ~6× superior a la que predice un modelo Binomial Negativo ajustado sobre las 51 comunas de la RM controlando por composición demográfica (extranjeros, desempleo, dependencia, brecha educativa, ofset poblacional), lo que la convierte en la observación más extrema de toda la distribución regional de residuos.
¿Qué notebook produce la figura headline?
notebooks/final_anomaly.ipynb


Tiempo aproximado de ejecución: ~30 segundos en un Colab estándar. El notebook no vuelve a correr el pipeline completo de las Tareas: carga directamente la tabla analítica final tarea3_analytical_table.csv (producida al cierre de Tarea 3) y re-ajusta solamente el modelo Negative Binomial necesario para extraer los residuos.


La figura headline (figs/headline.png) es un bar chart horizontal de los residuos de Pearson de las 51 comunas, con San Pedro resaltada en rojo y las tres comunas asignadas al par en azul.
Estructura del repositorio
iele756-region-1/


├── README.md


├── requirements.txt


├── notebooks/


│   ├── tarea0.ipynb


│   ├── tarea1.ipynb


│   ├── tarea2.ipynb


│   ├── tarea3.ipynb


│   └── final_anomaly.ipynb


├── data/


│   └── (rutas / script de descarga)


└── figs/


    ├── headline.png


    └── (figuras de diagnóstico)


La tabla maestra tarea3_analytical_table.csv se monta desde Google Drive en el notebook (ruta hardcodeada al directorio del equipo). Para reproducir fuera de Colab, ajustar la variable RUTA_TABLA en la celda 1 del notebook.
Instalación y reproducción
git clone https://github.com/Nitram0365/iele756-region-1.git


cd iele756-region-1


pip install -r requirements.txt


jupyter notebook notebooks/final_anomaly.ipynb


Dependencias principales: pandas, numpy, matplotlib, seaborn, statsmodels.


Para regenerar headline.png basta con ejecutar todas las celdas del notebook en orden (Runtime → Run all en Colab, o Cell → Run All en Jupyter). La figura queda guardada automáticamente en el directorio de trabajo.
Qué contiene final_anomaly.ipynb
1. Configuración e imports — definición de la comuna focal y las comunas del par.
2. Carga de la tabla maestra — lectura de tarea3_analytical_table.csv (51 comunas × 30 columnas) y verificación de la presencia de San Pedro.
3. Re-ajuste del modelo Binomial Negativo — idéntico al de Tarea 3, con offset poblacional y los mismos regresores demográficos. Extracción de residuos de Pearson y predicciones.
4. Aislamiento del número — ubicación de San Pedro en la distribución de residuos (ranking #1 de 51, z = +6.30).
5. Figura headline — bar chart de residuos, San Pedro en rojo, comunas del par en azul.
6. Explicaciones alternativas — dos chequeos en código:
   * 5.1 Artefacto por población pequeña: comparación con las 8 comunas más chicas de la RM. San Pedro tiene 731 casos sobre ~12.000 habitantes; comunas de tamaño similar (Alhué, María Pinto, San José de Maipo) presentan residuos negativos o cercanos a cero. El tamaño introduce volatilidad, pero no explica el patrón.
   * 5.2 Centralización hospitalaria provincial: los residuos de las 5 comunas de la Provincia de Melipilla (Melipilla, Curacaví, Alhué, María Pinto, San Pedro) muestran que San Pedro es la única con residuo fuertemente positivo; las otras cuatro son levemente negativas. No hay evidencia de un patrón provincial homogéneo.
7. Conclusión — tres a cuatro frases que coinciden con el cierre del video.
Cifras clave
Métrica
	Valor
	Tasa ENO observada en San Pedro
	609.17 / 10.000
	Tasa ENO predicha por el modelo
	107.69 / 10.000
	Residuo de Pearson
	+5.11
	z del residuo
	+6.30
	Ranking en la RM (51 comunas)
	#1 más positivo
	Media regional de residuos
	0.000
	SD regional de residuos
	0.811
	AIC del modelo NB
	797.64
	Deviance
	14.31
	Divulgación de uso de IA
Usamos Claude (Anthropic) durante el proyecto para los siguientes fines específicos:


* Guía y revisión del análisis: discutir con Claude la lógica del re-ajuste del modelo Binomial Negativo, validar la interpretación de los residuos de Pearson, y verificar que las explicaciones alternativas (artefacto por denominador chico, centralización hospitalaria) estuvieran correctamente planteadas y refutadas con evidencia del propio dataset.
* Mejora visual de la figura headline: Claude nos asistió en pulir el bar chart de residuos (esquema de colores rojo/azul/gris, líneas de referencia en ±2, layout, tamaños de fuente) para que la anomalía fuera legible de un solo vistazo.
* Redacción del README: Claude ayudó a estructurar este documento siguiendo los requisitos de la rúbrica (lectura en dos minutos, secciones obligatorias).
* Redacción de comentarios y celdas Markdown del notebook final, partiendo de borradores nuestros.


Todo el código del pipeline (Tareas 0 a 3) y la decisión sobre qué anomalía defender fueron nuestras. Revisamos línea a línea cada bloque de código que Claude sugirió, verificamos los números contra la tabla maestra, y somos plenamente responsables de cada cifra y cada afirmación de este repositorio.


No usamos otras herramientas de IA (ni Copilot, ni ChatGPT, ni asistentes de código integrados al IDE).
Enlaces
* Repositorio GitHub: https://github.com/Nitram0365/iele756-region-1
* Video (8–10 min):  https://youtu.be/wgup0y9Km8U
Contacto
Equipo 19 — Borja Landerretche · Martín Crisóstomo
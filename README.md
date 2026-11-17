# Agroindustrias del Tolima — presentación y dashboard académico

Sitio web estático, compatible con GitHub Pages. **Contiene 10 diapositivas**, dashboard de ocho modelos, tabla de fortalezas y debilidades, análisis de discrepancias, flujo híbrido y reflexión crítica.

## Publicación en GitHub Pages

1. Crea un repositorio en GitHub.
2. Sube `index.html`, `style.css`, `app.js`, `data.js` y opcionalmente los archivos de auditoría.
3. En **Settings → Pages**, selecciona **Deploy from a branch**, `main` y `/(root)`.
4. Abre la URL publicada que indique GitHub.

## Trazabilidad estadística

- Fuente: `1 taller(6).xlsx` (36 meses, enero 2024–diciembre 2026). Montos en **miles de COP**.
- `data_source.json`: transcripción de la serie y resultados originales de la hoja.
- `validar_modelos.py`: genera `data_validated.json` y `data.js`. Requiere `numpy` y `statsmodels`.
- Evaluación: 24 pronósticos retrospectivos **a un paso** con origen móvil expansivo; ningún modelo recibe el valor del mes que debe predecir.
- Modelos: último valor, promedio simple, PM12, SES α=0,9, Holt, regresión lineal, ARIMA(1,1,1) y estacional ingenuo.
- El MAPE más bajo en esta validación **no garantiza** el menor error de un pronóstico a seis meses. Faltan diagnóstico de residuos, intervalos de predicción calibrados y evaluación multihorizonte.
- Los escenarios porcentuales son **análisis de sensibilidad**, no intervalos de confianza.
- Los costos/gastos proyectados son estimaciones basadas en tasas históricas, no presupuestos aprobados.
- No se han fabricado resultados de un segundo proceso IA independiente.

Para reproducir: `python validar_modelos.py`. Para visualizar: abrir `index.html` o usar GitHub Pages.

# Clasificación de Residuos con TensorFlow

Este proyecto implementa y compara dos enfoques de redes neuronales para la clasificación de imágenes de residuos, utilizando el dataset "Real Waste" de Kaggle. El trabajo se realizó en un notebook de Python con TensorFlow y Keras, ejecutado en Google Colab.

## Resumen de lo realizado

- **Preparación de datos:**
	- Se descargó y organizó el dataset en Google Drive, estructurando las imágenes por clase.
	- Se dividieron los datos en conjuntos de entrenamiento, validación y prueba.
	- Se visualizaron ejemplos de cada clase para inspección inicial.

- **Modelado:**
	1. **Modelo desde cero (CNN):**
		 - Se construyó una red neuronal convolucional simple y se entrenó desde cero.
		 - Se evaluó el desempeño en el conjunto de prueba.
	2. **Transfer Learning (ResNet50V2):**
		 - Se utilizó un modelo pre-entrenado (ResNet50V2) como extractor de características.
		 - Se añadió y entrenó un clasificador propio sobre la base congelada.
		 - Se realizó fine-tuning de las últimas capas del modelo base.
		 - Se evaluó el desempeño en el conjunto de prueba.

- **Evaluación y comparación:**
	- Se calcularon métricas como accuracy y F1-score macro, además de F1-score por clase.
	- Se analizaron matrices de confusión y se identificaron las clases con mejor y peor desempeño.

## Principales conclusiones

- El modelo con Transfer Learning (ResNet50V2) superó ampliamente al modelo entrenado desde cero:
	- **Accuracy:** 73% (Transfer Learning) vs 49% (CNN desde cero)
	- **F1-score macro:** 0.72 (Transfer Learning) vs 0.47 (CNN desde cero)
- Las clases más fáciles de clasificar fueron `vegetation` y `food_organics`.
- La clase más difícil fue `miscellaneous`, debido a su alta heterogeneidad.
- El uso de modelos pre-entrenados permite una mejor generalización y rendimiento, especialmente con conjuntos de datos limitados.

## Recomendaciones de mejora

- Implementar técnicas de aumento de datos (data augmentation).
- Ajustar más capas del modelo pre-entrenado (fine-tuning).
- Probar otros modelos pre-entrenados (VGG, Inception, EfficientNet).
- Analizar errores específicos y mejorar la calidad de los datos.

## Aplicabilidad

El modelo basado en Transfer Learning es adecuado para prototipos, sistemas de soporte a la clasificación manual y aplicaciones con tolerancia a errores. Para aplicaciones críticas, se recomienda seguir optimizando el modelo y los datos.

---

Para más detalles, consultar el notebook `classification_tf.ipynb` donde se documenta el proceso completo, los experimentos y los resultados obtenidos.
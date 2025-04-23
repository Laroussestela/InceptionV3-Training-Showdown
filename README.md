# InceptionV3-Training-Showdown

## 📊 Objetivo

Comparar el rendimiento de InceptionV3 preentrenado sobre ImageNet utilizando las siguientes técnicas:

1. **Entrenamiento Base**: sin modificaciones adicionales.
2. **Batch Normalization**: se añade batch normalization a las capas entrenables.
3. **Data Augmentation**: se aplica aumento de datos durante el entrenamiento.
4. **Dropout**: se introducen capas dropout para prevenir overfitting.
5. **Weight Regularization**: se aplican penalizaciones L2 a los pesos.

Estas cinco configuraciones se aplican tanto **antes** como **después del fine-tuning** para analizar su impacto relativo.

## 🧠 Modelo base

- `InceptionV3` con pesos preentrenados en ImageNet.
- Últimas capas adaptadas a la tarea objetivo.

## Tabla de Resultados

| Modelo                          | Tipo         | Técnica | Épocas | Accuracy | Precision | Recall   | F1-score |
|---------------------------------|--------------|---------|--------|----------|-----------|----------|----------|
| model_fine_tuning_data_augm     | Fine-tuning  | augm    | 20     | 0.999333 | 0.999340  | 0.999333 | 0.999333 |
| model_fine_tuning_drop_out      | Fine-tuning  | out     | 13     | 0.945000 | 0.924221  | 0.945000 | 0.970344 |
| model_fine_tuning_batch_norm    | Fine-tuning  | norm    | 12     | 0.954000 | 0.923840  | 0.954000 | 0.966626 |
| model_fine_tuning_weight_regu   | Fine-tuning  | regu    | 11     | 0.950333 | 0.950836  | 0.950333 | 0.980707 |
| model_fine_tuning_normal        | Fine-tuning  | normal  | 19     | 0.920667 | 0.937944  | 0.920667 | 0.949555 |
| model_transf_learn_weight_regu  | Transfer     | regu    | 11     | 0.968000 | 0.967295  | 0.968000 | 0.888657 |
| model_transf_learn_data_augm    | Transfer     | augm    | 18     | 0.824333 | 0.871830  | 0.824333 | 0.828777 |
| model_transf_learn_normal       | Transfer     | normal  | 16     | 0.818000 | 0.881126  | 0.818000 | 0.824309 |
| model_transf_learn_drop_out     | Transfer     | out     | 12     | 0.760000 | 0.783436  | 0.760000 | 0.710484 |
| model_transf_learn_batch_norm   | Transfer     | norm    | 20     | 0.766667 | 0.744525  | 0.766667 | 0.798346 |




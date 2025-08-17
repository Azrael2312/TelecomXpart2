### 📊 Predicción de Rotación de Clientes de Telecomunicaciones

Este proyecto analiza la rotación de clientes para una compañía de telecomunicaciones utilizando modelos de aprendizaje automático. El objetivo es identificar los principales factores que impulsan la cancelación de clientes y proponer estrategias para mejorar la retención de clientes.

### 📂 Estructura del Proyecto

- `TelecomX_Cleaned.csv` # Conjunto de datos preprocesado
    
- `notebooks/` # Cuadernos de Jupyter/Colab con el análisis
    
- `models/` # Modelos entrenados (opcional)
    
- `README.md` # Documentación del proyecto
    

### 🚀 Pasos Realizados

#### 1. Preparación de Datos

- Se cargó el conjunto de datos ya limpio (`TelecomX_Cleaned.csv`).
    
- Se eliminaron las variables no informativas (`customerID`, `account.Daily_Accounts`).
    
- Se manejaron los valores faltantes en `Total Charges`.
    
- Se aplicó la codificación _one-hot_ para las variables categóricas.
    
- Se dividió el conjunto de datos en conjuntos de entrenamiento (80%) y prueba (20%) (estratificado por rotación).
    

#### 2. Modelos Entrenados y Evaluados

- Se entrenó y se comparó:
    
    - Regresión Logística
        
    - Máquina de Vectores de Soporte (SVM)
        
    - Random Forest
        
    - K-Nearest Neighbors (KNN)
        
- Cada modelo se evaluó con:
    
    - Precisión (_Accuracy_)
        
    - Precisión (_Precision_)
        
    - Cobertura (_Recall_)
        
    - Puntuación F1 (_F1 Score_)
        
    - Matriz de Confusión
        

### 3. Rendimiento del Modelo

|Modelo|Precisión (_Accuracy_)|Precisión (_Precision_)|Cobertura (_Recall_)|Puntuación F1 (_F1 Score_)|Conclusiones|
|---|---|---|---|---|---|
|**SVM**|0.74|0.51|**0.78**|**0.62**|El mejor equilibrio entre cobertura y F1. Excelente para detectar clientes que rotan.|
|**Regresión Logística**|0.74|0.51|**0.79**|**0.62**|Similar a SVM. Sencillo e interpretable, buena cobertura.|
|**Random Forest**|**0.79**|**0.63**|0.49|0.56|La mejor precisión y exactitud, pero con menor cobertura (pierde clientes que rotan).|
|**KNN**|0.75|0.54|0.49|0.51|Rendimiento inferior, no recomendado.|

### 4. Hallazgos Clave

- **Principales predictores de rotación** (de Regresión Logística, Random Forest e importancia de la permutación):
    
    - **Contrato mes a mes** → el factor más fuerte de rotación.
        
    - **Baja permanencia** → los clientes nuevos se van más rápido.
        
    - **Pago con cheque electrónico** → mayor riesgo de rotación.
        
    - **Falta de servicios adicionales** (seguridad en línea, protección de dispositivos, soporte técnico).
        
    - **Cargos mensuales altos y cargos de por vida bajos** → rotación sensible al costo.
        

### 5. Estrategias de Retención

- **Contrato y Lealtad:** Incentivar contratos más largos con descuentos.
    
- **Incorporación:** Enfocarse en los primeros 3 meses para reducir la rotación temprana.
    
- **Métodos de Pago:** Fomentar el pago automático/tarjeta de crédito y desaconsejar los cheques electrónicos.
    
- **Agrupación de Servicios:** Agregar valor con paquetes de seguridad y soporte.
    
- **Estrategia de Precios:** Ofrecer descuentos de retención a clientes con gastos mensuales altos en riesgo; promociones para usuarios de bajo gasto.
    
- **Contacto Proactivo:** Dirigirse a clientes nuevos, mensuales y usuarios de cheque electrónico con campañas de retención.
    

### ⚙️ Stack Tecnológico

- `Python 3.x`
    
- `Pandas`, `NumPy` (preprocesamiento de datos)
    
- `Scikit-learn` (modelos de ML, evaluación, escalado, SMOTE)
    
- `Matplotlib`, `Seaborn` (visualizaciones)
    
- `XGBoost` (modelo avanzado opcional)
    

### 📌 Siguientes Pasos

- Desplegar el modelo con mejor rendimiento (SVM / Regresión Logística) como una API de predicción de rotación.
    
- Integrar los resultados con el CRM del cliente para alertas de rotación en tiempo real.
    
- Probar métodos de _boosting_ (`XGBoost`, `LightGBM`) para mejoras adicionales.
    

### 👨‍💻 Autor

Este proyecto fue desarrollado como parte de un caso de estudio de Ciencia de Datos en la predicción de la rotación de clientes.

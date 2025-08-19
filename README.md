"""
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
~ .oooooo..o  o8o            o8o                          oooooooooo.  oooo       ~
~d8P'    `Y8  `"'            `"'                          `888'   `Y8b `888       ~
~Y88bo.      oooo  oooo d8b oooo  oooo  oooo   .oooo.o     888     888  888  oooo ~
~ `"Y8888o.  `888  `888""8P `888  `888  `888  d88(  "8     888oooo888'  888 .8P'  ~
~     `"Y88b  888   888      888   888   888  `"Y88b.      888    `88b  888888.   ~
~oo     .d8P  888   888      888   888   888  o.  )88b     888    .88P  888 `88b. ~
~8""88888P'  o888o d888b    o888o  `V88V"V8P' 8""888P'    o888bood8P'  o888o o888o~
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
"""

# Telecom X_1: Análisis Exploratorio de Datos (EDA) de Churn en Telecomunicaciones

Proyecto de análisis exploratorio de datos para identificar patrones y factores asociados a la cancelación de clientes (churn) en una empresa de telecomunicaciones.  
Desarrollado por Adrián | Branding: SiriusBk  

---

##  Objetivo  
Explorar y visualizar relaciones clave en los datos de clientes para entender qué variables (género, tipo de contrato, cargos mensuales, etc.) están más asociadas al churn.  

---

##  Metodología  

### 1. **Extracción y Transformación**  
- Carga de datos desde un archivo JSON.  
- Normalización de estructuras anidadas.  
- Limpieza y conversión de tipos:  
  - Columnas binarias (`Churn`, `Partner`) convertidas a booleanos.  
  - Variables categóricas (`PaymentMethod`, `Contract`) tipificadas como `category`.  
  - Manejo de valores nulos en `Charges.Total` (imputación con la mediana).  
  - Validación de formatos en `customerID` (ejemplo: `1234-ABCDE`).  

### 2. **Análisis Exploratorio**  
- Visualización de distribuciones y relaciones mediante:  
  - Gráficos de barras (churn por género, contrato, método de pago).  
  - Histogramas (cargos mensuales vs. churn).  
  - Heatmaps (correlaciones entre variables numéricas).  
  - Gráficos de dispersión (relación entre cargos mensuales y totales).  

---

##  Principales Hallazgos  

###  **Distribución de Churn**  
- **27% de los clientes cancelaron** el servicio (desequilibrio de clases típico en churn).  
- **Variables clave asociadas**:  
  - **Contrato**: Clientes con contratos mensuales tienen mayor churn (≈43%) vs. bienales (≈12%).  
  - **Antigüedad (`tenure`)**: Clientes nuevos (<6 meses) son más propensos a cancelar.  
  - **Cargos mensuales**: Clientes que pagan >$90 tienen mayor tasa de churn.  

###  **Correlaciones**  
- **Negativa fuerte**: `tenure` vs. `Churn` (-0.35).  
- **Positiva fuerte**: `Charges.Monthly` vs. `Charges.Total` (0.65).  

###  **Servicios Adicionales**  
- Clientes con **soporte técnico (`TechSupport`) o seguridad en línea (`OnlineSecurity`)** presentan menor churn.  

---


Recomendaciones Iniciales

Focalizar retención en clientes con contratos mensuales y antigüedad <6 meses.
Revisar precios de planes con cargos >$90 para mejorar percepción de valor.
Promover servicios adicionales (ej: soporte técnico) como estrategia de fidelización.

Tecnologías Utilizadas
Python: pandas, numpy, seaborn, matplotlib.

Herramientas: Google Colab, Jupyter Notebook.

Cómo Reproducir

git clone https://github.com/SiriusBK1/Challenge-Telecom-X_1
pip install -r requirements.txt  # pandas, seaborn, matplotlib
jupyter notebook Telecom_X_1_EDA.ipynb


👤 Autor
Adrián — Estudiante de Data Science
🔗 GitHub: SiriusBk
📬 Contacto: aacevedovergara@gmail.com

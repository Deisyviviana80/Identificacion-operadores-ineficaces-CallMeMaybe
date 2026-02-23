# 📞 Identificación de Operadores Ineficaces - CallMeMaybe

## Descripción del Proyecto

Este proyecto analiza los datos de llamadas del servicio de telefonía virtual **CallMeMaybe** con el objetivo de identificar a los operadores menos eficaces. Los resultados permiten a los supervisores tomar decisiones informadas sobre redistribución de tareas, capacitación del personal o contratación.

El proyecto fue desarrollado como **Proyecto Final** del programa de formación en análisis de datos de **TripleTen**.

---

## 🎯 Objetivo

Identificar operadores ineficaces con base en tres métricas clave, definidas estadísticamente mediante cuartiles:

| Métrica | Criterio de ineficiencia |
|---------|--------------------------|
| Tasa de llamadas perdidas | Operadores en el **cuartil superior (Q3)** |
| Tiempo promedio de espera | Operadores en el **cuartil superior (Q3)** |
| Número de llamadas salientes | Operadores en el **cuartil inferior (Q1)** |

---

## 🗂️ Datasets

| Archivo | Descripción |
|---------|-------------|
| `telecom_clients_us.csv` | Información de clientes: plan tarifario y fecha de inicio |
| `telecom_dataset_us.csv` | Registro detallado de llamadas: dirección, duración, llamadas perdidas, operador asignado |

---

## 🔍 Hallazgos Principales

### Operadores identificados
De un total de **1,093 operadores**, se clasificaron **326 como ineficaces (30%)**, al cumplir al menos uno de los tres criterios definidos.

### Pruebas de Hipótesis

| Hipótesis | Resultado |
|-----------|-----------|
| H1: Operadores con alta tasa de pérdida tienen mayor tiempo de espera | ✅ Confirmada — diferencia estadísticamente significativa |
| H2: Operadores ineficaces realizan un número diferente de llamadas salientes | ⬜ No confirmada — p = 0.197, sin diferencia significativa |

### Conclusiones Clave
- La ineficiencia está principalmente asociada a la **gestión de llamadas entrantes**: alta tasa de pérdida y tiempos de espera elevados van de la mano.
- El volumen de llamadas salientes no resultó ser un diferenciador estadístico entre operadores eficaces e ineficaces.
- Se detectaron **8,172 registros sin operador identificado** (`operator_id` nulo) que requieren investigación por parte de la administración.

---

## 💡 Recomendaciones

- **Entrenamiento focalizado** en gestión de tiempos de respuesta para los operadores del cuartil superior.
- **Redistribución de tareas** usando las métricas para equilibrar cargas de trabajo.
- **Investigar los registros sin operador** para determinar si son errores del sistema o llamadas realmente no atendidas.
- **Monitoreo continuo** con dashboards en tiempo real para supervisores.
- **Establecer KPIs formales** de tasa de llamadas perdidas y tiempo de espera aceptables.

---

## 🛠️ Tecnologías Utilizadas

- **Python 3**
- **pandas** — manipulación y análisis de datos
- **scipy** — pruebas estadísticas T de muestras independientes
- **matplotlib / seaborn** — visualización de datos
- **Jupyter Notebook** — entorno de desarrollo

---

## 📁 Archivos del Repositorio

```
📦 telecom-operadores-ineficaces
 ┣ 📓 Telecom.ipynb                  # Notebook principal con el análisis completo
 ┣ 📄 telecom_clients_us.csv         # Datos de clientes
 ┣ 📄 telecom_dataset_us.csv         # Registros de llamadas
 ┗ 📄 README.md                      # Este archivo
```

---

## ▶️ ¿Cómo ejecutar el proyecto?

```bash
# Instalar dependencias
pip install pandas scipy matplotlib seaborn jupyter

# Abrir el notebook
jupyter notebook Telecom.ipynb
```

---

## 👩‍💻 Autora

Proyecto desarrollado como **Proyecto Final** del programa de **Análisis de Datos — TripleTen**.

**Deisy Viviana Hurtado Vega**
deisyviviana80@gmail.com

---

*Este repositorio forma parte de mi portafolio de proyectos de análisis de datos.*

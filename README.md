# 📉 Telecom X — Predicción de Cancelación (Churn)

Proyecto de **Machine Learning** para analizar y predecir la **cancelación de clientes (churn)** en una empresa de telecomunicaciones.  
Incluye **preprocesamiento**, **balanceo de clases**, **entrenamiento de modelos** y un **análisis de variables clave** para proponer **estrategias de retención** basadas en evidencia.

---

## 🚀 Objetivo

1. **Identificar** los factores que más influyen en la cancelación.
2. **Entrenar** modelos de clasificación para predecir churn.
3. **Comparar** desempeño entre modelos.
4. **Proponer estrategias** de retención accionables para el negocio.

---

## 🧠 Modelos usados

- **Regresión Logística**
  - Alta interpretabilidad (coeficientes).
  - Buena capacidad para detectar churn (recall alto).
- **Árbol de Decisión**
  - Captura relaciones no lineales.
  - Útil para ver variables relevantes vía *feature importance*.

> Ambos modelos obtuvieron alrededor de **74% de exactitud**.  
> La **Regresión Logística** destacó por **recall > 80%**, ideal para detectar clientes con riesgo de cancelación.

---

## 🧹 Preprocesamiento (pipeline)

- Eliminación de identificadores (`cliente_id`)
- Codificación de variables categóricas (**one-hot encoding**)
- Evaluación del desbalance de clases (Churn ≈ 25.7%)
- Balanceo con **SMOTE**
- Normalización/estandarización cuando aplica (modelos sensibles a escala)

---

## 🔍 Hallazgos principales (variables influyentes)

### 📌 Regresión Logística (coeficientes)
**Factores que aumentan el riesgo de churn**
- **Internet por fibra óptica** (mayor impacto positivo)
- **Contrato mes a mes**
- **Facturación sin papel**
- **Cargo mensual** (a mayor costo, mayor riesgo)

**Factores protectores**
- **Servicio telefónico**
- **Seguridad en línea**
- **Soporte técnico**
- **Tener pareja (Partner)**

> Nota curiosa: métodos de pago automáticos aparecieron como factor de riesgo en el análisis, lo cual sugiere investigar causas operativas (cobros, fricción, cambios rápidos de proveedor, etc.).

---

### 🌳 Árbol de Decisión (importancia de variables)
- **Antigüedad (meses)** → predictor más fuerte (clientes nuevos cancelan más)
- **Cargo total** y **cargo mensual**
- **Tipo de internet (fibra óptica)**
- **Tipo de contrato**
- `Cuentas_Diarias` (feature derivada) con relevancia moderada

---

## 🧩 Síntesis: ¿Qué está empujando el churn?

✅ Riesgo alto asociado a:
- Fibra óptica  
- Contrato mes a mes  
- Facturación sin papel  
- Altos cargos  
- Baja antigüedad  

✅ Retención natural asociada a:
- Servicios extra (seguridad, soporte, phone)  
- Contratos largos  
- Mayor antigüedad  

---

## 📈 Estrategias de retención propuestas (data-driven)

### 1) 🎯 Fidelización de usuarios con fibra óptica
- Encuestas de satisfacción específicas
- Mejoras de velocidad/promos temporales
- Atención técnica prioritaria (SLA más rápido)

### 2) 🧾 Migración a contratos de largo plazo
- Descuentos por 12/24 meses
- Beneficios por permanencia (servicios incluidos, precios fijos)

### 3) 📨 Revisión de facturación sin papel
- Evaluar fricción digital / comunicación
- Recordatorios personalizados
- Incentivos por facturación electrónica

### 4) 💸 Segmentación por cargo mensual + antigüedad
- Campañas para **alto cargo + baja antigüedad** (primeros 3–6 meses)
- Contacto proactivo a clientes que superen umbrales de gasto

### 5) 🛡️ Promover servicios de valor agregado
- Bundles: internet + seguridad + soporte
- Activación simple / prueba gratuita por 1–3 meses

### 6) 💳 Analizar métodos de pago automáticos
- Revisar fallos de cobro / experiencias
- Facilitar cambios de método
- Alertas previas a cortes y cobros

---

## 📂 Estructura del repo (sugerida)


# 📊 Simulación de Distribuciones de Probabilidad con Python

## 🚀 ¿Qué hace este código?

Este proyecto implementa la **simulación de cuatro distribuciones de probabilidad** utilizando el **método de la transformada inversa** (también conocido como método de la función de distribución acumulada inversa). 

Se generan **~5000 muestras aleatorias** para cada una de las siguientes distribuciones:

| Distribución | Parámetros | Método de Simulación |
|:---|:---|:---|
| **Uniforme (-1, 1)** | `a = -1`, `b = 1` | `x = 2u - 1` |
| **Exponencial (1)** | `λ = 1` | `x = -ln(1 - u)` |
| **Cauchy (5, 4)** | `x₀ = 5`, `γ = 4` | `x = 4·tan(π(u - 0.5)) + 5` |
| **Laplace (0, 0.5)** | `α = 0`, `β = 0.5` | `x = (ln(2u))/2` si `u < 0.5`, o `x = -(ln(2 - 2u))/2` si `u ≥ 0.5` |

*(donde `u` es un número aleatorio uniforme entre 0 y 1)*

---

## 📈 ¿Qué resultados obtuvo?

### ✅ Comparación Visual: Histograma vs. Densidad Teórica

Para cada distribución se generó una figura con **dos gráficos lado a lado**:

- **Histograma** de las muestras simuladas (barras azules)
- **Curva de densidad teórica** (línea roja)

Esto permite validar visualmente que las muestras simuladas **se ajustan correctamente a la distribución esperada**.

### 📊 Comparación de Estadísticos

Se calcularon y compararon **media y varianza muestrales** versus sus **equivalentes teóricos**:

| Distribución | Media Teórica | Media Muestral | Varianza Teórica | Varianza Muestral |
|:---|:---|:---|:---|:---|
| **Uniforme(-1,1)** | `0` | `≈ -0.00042` ✅ | `0.3333` | `≈ 0.3334` ✅ |
| **Exponencial(1)** | `1` | `≈ 0.98` ✅ | `1` | `≈ 0.968` ✅ |
| **Cauchy(5,4)** | **No existe** | `≈ 6.04` ❗ | **No existe** | `≈ 51524` ❗ |
| **Laplace(0,0.5)** | `0` | `≈ 0` ✅ | `0.5` | `≈ 0.5` ✅ |

> ❗ **Nota:** La distribución de Cauchy **no tiene media ni varianza definidas** matemáticamente. Por eso los valores muestrales son tan inestables y cambian drásticamente con cada simulación, lo cual es **un comportamiento esperado y una demostración perfecta de esta propiedad**.

---

## 🧠 Principales Aprendizajes

- ✅ El **método de la transformada inversa** es una herramienta poderosa y sencilla para generar muestras de cualquier distribución.
- ✅ La **ley de los grandes números** se cumple: la media y varianza muestrales convergen a los valores teóricos cuando el número de muestras es grande.
- ✅ La **distribución de Cauchy** es un gran ejemplo de **distribución de colas pesadas** sin momentos definidos.
- ✅ La visualización simultánea (**histograma + densidad teórica**) es una forma rápida y confiable de validar simulaciones.

---

## 🛠️ Tecnologías Utilizadas

- 🐍 **Python 3.8+**
- 📓 **Jupyter Notebook**
- 🔢 **NumPy** – para cálculos numéricos
- 📊 **Matplotlib** – para visualización de gráficos
- 🎲 **Random** – para generación de números pseudoaleatorios
- 🧮 **Math** – para funciones matemáticas (`log`, `tan`, `exp`, etc.)

---

## 📂 Estructura del Proyecto

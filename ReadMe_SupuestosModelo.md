# ⚠️ DISCLAIMER Y SUPUESTOS DEL MODELO

## 📋 Información Importante para Usuarios del Pipeline

Este documento describe las limitaciones, supuestos y consideraciones técnicas del **Predictive People Analythics with RNA**. Es fundamental leer y comprender estos puntos antes de utilizar o interpretar los resultados del modelo.

---

## 🚫 Limitaciones de los Datos

### 📊 Datos completamente artificiales
Los datos utilizados en este pipeline son **generados sintéticamente** y no reflejan información de ninguna organización real. Todos los valores, patrones y relaciones son producto de algoritmos de simulación.

### 🎓 Propósito académico/demostrativo
Este proyecto tiene fines **educativos y de demostración técnica**. Su objetivo es mostrar capacidades de desarrollo de pipelines de machine learning, no proporcionar insights empresariales reales.

### ❌ No usar para decisiones reales
Los resultados, predicciones y presupuestos generados **NO deben aplicarse en entornos empresariales** sin validación previa con datos reales y contexto organizacional específico.

---

## 🏗️ Supuestos de Estructura de Datos

### 📋 Incompletitud de datos históricos
El dataset **no es un registro completo** de cada combinación (Proyecto, Área, Trimestre) a lo largo de los cuatro años. Representa un **muestreo disperso y no uniforme** de datos operativos con recolección irregular, simulando condiciones reales donde la información puede tener gaps temporales.

### 🔍 Desajuste de granularidad
Los 1500 registros **simulan un entorno real** donde los datos se recopilan con granularidad más fina que la trimestral (mensuales, semanales o por eventos), posteriormente agregados para análisis trimestral. Esta estructura refleja la complejidad típica de sistemas de información empresariales.

### 🔄 Ciclos de vida del proyecto
El modelo usa el **estado más reciente conocido** de cada combinación proyecto-área para proyecciones futuras, aplicando `drop_duplicates(keep='last')` como enfoque práctico que prioriza la información más actualizada disponible.

### 📐 Lógica de pronóstico estructurado
El pipeline genera una **cuadrícula uniforme** de puntos futuros (28 proyectos × 4 trimestres = 112 registros) basada en entidades históricas únicas, creando un formato predecible para planificación empresarial.

---

## 📊 Supuestos de Generación de Datos

### 🎲 Distribución Poisson para dotación
Modela **eventos discretos** (número de empleados) con tasa promedio fija, apropiada para conteos de personal donde los valores son enteros positivos y siguen un patrón de frecuencia específico.

### 📈 Distribución Normal para costos y horas
Refleja **variables continuas** que tienden a concentrarse alrededor de un promedio con variación simétrica, característica típica de costos salariales y horas trabajadas en contextos organizacionales.

### 📏 Distribución Uniforme para carga laboral
Asume **equiprobabilidad** en el rango de capacidad operativa (subcarga a sobrecarga), modelando situaciones donde la carga de trabajo puede variar uniformemente entre límites definidos.

### 🎯 Distribución Binomial para ingresos/ceses
Modela **decisiones binarias independientes** (contratar/no contratar, cesar/no cesar) para cada empleado, donde cada "experimento" tiene una probabilidad fija de éxito.

---

## 🤖 Supuestos del Modelo Predictivo

### 💰 Factores de costo considerados
- **3.2x para ingresos**: Incluye costo trimestral completo más gastos de reclutamiento y onboarding
- **1.5x para ceses**: Contempla liquidación básica más beneficios sociales y costos de transición

### 📈 Crecimiento constante
Asume un **5% de crecimiento trimestral** en variables operacionales, simulando expansión organizacional sostenida sin considerar fluctuaciones económicas.

### 📊 Patrones históricos
El modelo **asume que las tendencias pasadas se mantienen** en el futuro, sin considerar cambios disruptivos en el mercado laboral, industria o estrategia empresarial.

### 🔒 Variables exógenas constantes
**Eventos externos, crisis económicas y cambios organizacionales** se consideran constantes durante el período de proyección y no se incluyen como variables predictivas en el modelo.

---

## 🎯 Recomendaciones de Uso

1. **Validar supuestos**: Revisar si los supuestos del modelo aplican al contexto específico de uso
2. **Calibrar parámetros**: Ajustar distribuciones y factores según datos reales de la organización
3. **Validación cruzada**: Comparar predicciones con resultados reales para evaluar precisión
4. **Monitoreo continuo**: Actualizar el modelo regularmente con nueva información

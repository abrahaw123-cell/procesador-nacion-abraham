# procesador-nacion-abraham
Simulación cuántica interactiva a temperatura ambiente — sin hardware especializado
# ⚛️ Procesador Nación Abraham

### Simulación Cuántica Interactiva a Temperatura Ambiente

[![Python](https://img.shields.io/badge/Python-3.8+-blue?style=flat-square&logo=python)](https://python.org)
[![Qiskit](https://img.shields.io/badge/Qiskit-0.45+-6929C4?style=flat-square&logo=qiskit)](https://qiskit.org)
[![HTML](https://img.shields.io/badge/App_Web-HTML%2FJS-orange?style=flat-square)](./procesador-nacion-abraham.html)
[![License](https://img.shields.io/badge/Licencia-MIT-green?style=flat-square)](./LICENSE)

-----

## 💡 Motivación

La computación cuántica suele presentarse como algo exclusivo de laboratorios con millones de dólares, refrigeración criogénica a milikelvin y hardware especializado que pocas instituciones en el mundo pueden costear.

**Este proyecto demuestra que eso no tiene que ser así.**

Con una computadora convencional y software de acceso libre, es posible simular el comportamiento real de un qubit, incluyendo ruido térmico, decoherencia y fidelidad cuántica, todo a temperatura ambiente. El objetivo es hacer la computación cuántica accesible: que cualquier persona con curiosidad y una laptop pueda ver, tocar y entender qué hace realmente una computadora cuántica, sin necesidad de grandes máquinas.

-----

## 🎯 ¿Qué demuestra este proyecto?

- Que un circuito cuántico con **ruido térmico real** (modelo T1/T2) puede simularse sin hardware especializado
- Que la **fidelidad cuántica a temperatura ambiente** sigue siendo útil y medible
- Que el verdadero obstáculo de los sistemas cuánticos físicos es el **costo de refrigeración**, no el concepto en sí
- Que la computación cuántica puede ser **visual, interactiva y educativa** desde el navegador

-----

## 🗂️ Estructura del repositorio

```
procesador-nacion-abraham/
│
├── procesador_nacion_abraham.py     # Simulación principal con Qiskit
├── procesador-nacion-abraham.html   # Aplicación web interactiva (sin dependencias)
├── requirements.txt                 # Dependencias de Python
└── README.md
```

-----

## ⚙️ Stack tecnológico

|Componente          |Tecnología                        |
|--------------------|----------------------------------|
|Simulación cuántica |Python + Qiskit + Qiskit-Aer      |
|Modelo de ruido     |`thermal_relaxation_error` (T1/T2)|
|Backend             |`qasm_simulator`                  |
|Visualización Python|Matplotlib                        |
|App web interactiva |HTML + CSS + JavaScript (vanilla) |

-----

## 🚀 Cómo ejecutar

### Opción 1 — App web (sin instalación)

Abre el archivo `procesador-nacion-abraham.html` directamente en cualquier navegador moderno. No requiere instalar nada.

### Opción 2 — Simulación Python

**Instalar dependencias:**

```bash
pip install -r requirements.txt
```

**Ejecutar:**

```bash
python procesador_nacion_abraham.py
```

Esto generará los gráficos de:

- Distribución de mediciones y esfera de Bloch (2D)
- Fidelidad cuántica vs temperatura
- Comparativa con sistemas del mercado (IBM, Honeywell, Intel)

-----

## 📦 requirements.txt

```
qiskit>=0.45.0
qiskit-aer>=0.13.0
numpy>=1.24.0
matplotlib>=3.7.0
```

-----

## 🔬 El circuito cuántico

```
q[0] ──[ RZ(θ) ]──[ H ]──●──
```

El procesador aplica una rotación `RZ` con ángulo configurable (`angulo_h = 142.37°` por defecto), seguida de una compuerta Hadamard que lleva el qubit a superposición. El resultado se mide bajo un modelo de ruido térmico con:

- **T1 = 50,000 ns** (tiempo de relajación)
- **T2 = 40,000 ns** (tiempo de decoherencia)
- **Tiempo de compuerta = 100 ns**

-----

## 📊 Resultados a temperatura ambiente (298K)

|Métrica                       |Valor             |
|------------------------------|------------------|
|Temperatura de operación      |298 K (ambiente)  |
|Fidelidad cuántica            |~0.9984           |
|Consumo de refrigeración      |~10.6 L/1000 shots|
|Ahorro vs sistemas criogénicos|~88.8%            |

-----

## 🌐 Aplicación web interactiva

La app web (`procesador-nacion-abraham.html`) permite explorar el sistema en tiempo real:

- **Slider de temperatura** — observa cómo la fidelidad cae al aumentar el calor
- **Slider de ángulo RZ** — controla la rotación del qubit y ve el vector de Bloch moverse
- **Slider de shots** — cambia el número de mediciones y observa la distribución
- **Esfera de Bloch animada** — visualización 3D del estado cuántico en tiempo real
- **Terminal de logs** — registro de cada simulación ejecutada
- **Tabla comparativa** — tu sistema vs IBM, Honeywell e Intel

-----

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Si tienes ideas para mejorar la precisión del modelo de ruido, agregar nuevos circuitos o mejorar la visualización, abre un issue o un pull request.

-----

## 📄 Licencia

MIT — libre para usar, modificar y distribuir.

-----

*Proyecto desarrollado con la convicción de que la computación cuántica debe ser accesible para todos.*

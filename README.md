# Sintetizador de sonidos respiratorios pediátricos

## Descripción

El **Sintetizador de sonidos respiratorios pediátricos** es una aplicación desarrollada en Python con interfaz gráfica basada en Tkinter que permite generar sonidos respiratorios sintéticos para pacientes sanos y pacientes asmáticos.

La aplicación genera un ciclo respiratorio sintético utilizando diccionarios de patrones de energía previamente construidos a partir de SPRSound, base de datos específica de sonidos respiratorios pediátricos

El sintetizador, permite:

- Modificar diferentes parámetros de la sibilancia.
- Visualizar la señal temporal.
- Visualizar el espectrograma tiempo-frecuencia.
- Escuchar el sonido generado.
- Guardar el audio en formato WAV.

---

# Características

- Interfaz gráfica intuitiva.
- Generación de respiración sintética mediante diccionarios K-Means.
- Simulación de pacientes sanos y asmáticos.
- Configuración completa de las sibilancias:
- Representación gráfica de:
  - Señal temporal.
  - Espectrograma.
- Reproducción de audio.
- Exportación en formato WAV.

---

# Requisitos del sistema

## Sistema operativo

Compatible con:

- Windows 10/11
- Linux
- macOS

---

## Lenguaje de programación: Python

Se recomienda utilizar la siguiente versión:

- Python 3.13 o superior
  
---

## Requisitos de hardware

Se recomienda disponer de:

- Procesador: 2 núcleos o superior.
- Memoria RAM: 4 GB (8 GB recomendados).
- Espacio en disco: 200 MB libres.
- Resolución de pantalla: 1280 × 720 o superior.
- Tarjeta de sonido y altavoces o auriculares.

---

## Librerías necesarias

La aplicación requiere las siguientes librerías:

| Librería | Uso |
|----------|-----|
| tkinter | Interfaz gráfica |
| numpy | Procesamiento numérico |
| matplotlib | Visualización de gráficos |
| scipy | Procesamiento de señales y escritura WAV |
| sounddevice | Reproducción de audio |
| pillow (PIL) | Carga y escalado de imágenes |
| pickle | Carga de diccionarios entrenados |

---

# Estructura del proyecto

```
Proyecto/
│
├── Sintetizador.py
│
├── Diccionarios/
│   ├── Di.pkl
│   └── De.pkl
│
├── Media/
│   ├── logo epsl.png
│   └── logo uja.png
│
└── README.md
```

---

# Archivos necesarios

La aplicación necesita obligatoriamente la siguiente estructura:

## Diccionarios

```
Diccionarios/
    Di.pkl
    De.pkl
```

Estos archivos contienen los patrones respiratorios utilizados para sintetizar la inspiración y la espiración.

Si alguno de ellos falta, la aplicación no podrá iniciarse.

---

## Imágenes (OPCIONAL)

```
Media/
    logo epsl.png
    logo uja.png
```

Estos archivos son opcionales y únicamente se utilizan para mostrar los logotipos en la interfaz.

---

# Ejecución

Desde la carpeta del proyecto ejecutar:

```bash
python Sintetizador.py
```

La aplicación localizará automáticamente:

- Los dos diccionarios.
- Las dos imágenes.

---

# Flujo de funcionamiento

## 1. Seleccionar el tipo de paciente

La aplicación permite seleccionar:

- Paciente sano
- Paciente asmático

Cuando se selecciona un paciente sano, los controles relacionados con la sibilancia están deshabilitados.

Cuando se selecciona un paciente asmático, los controles relacionados con la sibilancia quedan habilitados automáticamente.

---

## 2. Configurar la sibilancia (solo paciente asmático)

Se pueden modificar:

- **Frecuencia (Hz):** Entre 60 y 1000
- **Duración (s):** Entre 0,2 y 2,0 s
- **Pendiente:** Entre −50 y 50
- **Vibrato (Hz):** Entre 0 y 6
- **SNR, Relación señal/ruido (dB):** Entre −20 y 20 dB
- **Tipo de sibilancia:** Monofónica o Polifónica
- **Número de armónicos:** 0, 1 o 2
- **Fase respiratoria:** Inspiración o Espiración

---

## 3. Generar audio

Pulsar el botón:

```
GENERAR AUDIO
```

La aplicación sintetiza automáticamente un nuevo ciclo respiratorio.

---

## 4. Visualización

Se muestran dos representaciones:

- Señal temporal.
- Espectrograma. Características del espectrograma:

| Parámetro | Valor |
|-----------|-------|
| Tipo de representación | STFT |
| Frecuencia de muestreo | 4000 Hz |
| Enventanado | Hanning |
| Resolución temporal | 9 ms |
| Resolución frecuencial | 15,6 Hz |
| Rango de frecuencias visualizado | 0–1000 Hz |

---

## 5. Reproducción

Mediante el botón:

```
REPRODUCIR
```

El audio sintetizado se reproduce utilizando la tarjeta de sonido del sistema.

Puede detenerse mediante:

```
PAUSAR
```

---

## 6. Guardado

Mediante el botón:

```
GUARDAR
```

El sonido se exporta en formato:

```
.wav
```

---

# Salidas generadas

La aplicación genera:

- Señal respiratoria sintética.
- Espectrograma.
- Archivo WAV exportable.

---

# Autor

**Antonio Carrasco Garrido**

Escuela Politécnica Superior de Linares

*Universidad de Jaén*

Año 2026

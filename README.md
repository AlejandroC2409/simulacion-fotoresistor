# Simulación de Fotoresistores

## 📌 Descripción
Este proyecto simula el comportamiento de la resistencia en un fotoresistor en función de la temperatura y la iluminación. Está diseñado para analizar materiales semiconductores como **CdS** y **CdSe** y su respuesta a distintas condiciones ambientales. Se basa en modelos físicos que consideran la generación y recombinación de portadores de carga, así como la influencia de la temperatura y la iluminación en la conductividad del material.

##  Fundamentos Teóricos
Los fotoresistores son dispositivos semiconductores cuya resistencia eléctrica varía en función de la intensidad luminosa que incide sobre ellos. Este comportamiento se debe a la generación de pares electrón-hueco cuando los fotones con suficiente energía impactan el material. En este proyecto, se modelan las siguientes ecuaciones fundamentales:

1. **Densidad intrínseca de portadores**:
   \[
   n_i = \sqrt{N_c N_v} e^{-E_g / (2 k_B T)}
   \]
   Donde:
   - \( N_c \) y \( N_v \) son las densidades de estados efectivos en la banda de conducción y valencia.
   - \( E_g \) es la energía de banda prohibida del material.
   - \( k_B \) es la constante de Boltzmann.
   - \( T \) es la temperatura absoluta.

2. **Conductividad del material en oscuridad**:
   \[
   \sigma_{oscuridad} = q ( \mu_n n_0 + \mu_p p_0 )
   \]
   Donde:
   - \( \mu_n \) y \( \mu_p \) son las movilidades de electrones y huecos.
   - \( n_0 \) y \( p_0 \) son las concentraciones en equilibrio térmico.

3. **Generación de portadores debido a la iluminación**:
   \[
   \Delta n = \frac{\alpha I_0 e^{-\alpha x}}{h c / \lambda} \tau
   \]
   Donde:
   - \( \alpha \) es el coeficiente de absorción del material.
   - \( I_0 \) es la intensidad luminosa incidente.
   - \( \lambda \) es la longitud de onda de la luz incidente.
   - \( \tau \) es el tiempo de vida medio de los portadores.

4. **Resistencia bajo iluminación**:
   \[
   R_{luz} = \frac{L}{\sigma_{luz} A}
   \]
   Donde \( \sigma_{luz} \) es la conductividad con la luz incidente y \( A \) es el área del fotoresistor.

##  Características del Proyecto
- Simulación de la resistencia en **oscuridad** y **bajo iluminación**.
- Modelado basado en ecuaciones de semiconductores.
- Variación de resistencia con **temperatura** e **intensidad luminosa**.
- Gráficos de comportamiento con **Matplotlib**.
- Entrada interactiva para el usuario.
- Implementación flexible que permite modificar parámetros como el dopaje y la geometría del dispositivo.

##  Estructura del Proyecto
```
 ┣ fisica_de_semiconductores.py  # Código principal de simulación
 ┣ README.md                     # Documentación del proyecto
 ┗ dist/                          # Ejecutable generado con PyInstaller
```

##  Instalación y Uso
Este proyecto requiere **Python 3** y las siguientes librerías:
```sh
pip install numpy matplotlib
```

### **Ejecutar la Simulación**
#### **Desde Python**
Para ejecutar la simulación desde Python, abre una terminal y escribe:
```sh
python fisica_de_semiconductores.py
```

#### **Desde el Ejecutable**
Si deseas ejecutar la simulación sin necesidad de Python, usa el archivo generado en la carpeta `dist/`:
```sh
dist\fisica_de_semiconductores.exe
```
Esto abrirá el programa en la terminal y pedirá los siguientes parámetros de entrada:
1. **Temperatura** en °C (-30 a 80).
2. **Concentración de aceptores (Na)** en cm⁻³.
3. **Concentración de donadores (Nd)** en cm⁻³.
4. **Material** del fotoresistor (**CdS** o **CdSe**).
5. **Área del fotoresistor** en m² (1e-6 a 1e-4).
6. **Longitud del fotoresistor** en m (1e-4 a 1e-2).
7. **Intensidad luminosa** en lux (1 a 100).

El programa calculará la resistencia en **oscuridad** y **bajo iluminación**, además de generar gráficos de variación de la resistencia con la temperatura y la iluminación.

## Resultados
El programa generará dos gráficos:
1. **Variación de la resistencia con la temperatura**: muestra cómo cambia la resistencia en función de la temperatura en ausencia de luz.
2. **Variación de la resistencia con la iluminación**: representa la resistencia en función de la intensidad luminosa incidente.

2. **Resistencia en oscuridad**: representa la resistencia en el caso de total oscuridad, la cual para algunos usos sirve como referencia.

## 🛠 Tecnologías Usadas
- **Python 3**
- **NumPy** para cálculos numéricos.
- **Matplotlib** para visualización de datos.
- **PyInstaller** para la generación de ejecutables.


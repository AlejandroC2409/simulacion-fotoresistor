# Simulación de Fotoresistores

## Descripción
Este proyecto simula el comportamiento de la resistencia en un fotoresistor en función de la temperatura y la iluminación. Está diseñado para analizar semiconductores basados en Sulfuro de Cadmio (**CdS**) y seleniuro de Cadmio (**CdSe**), ya que son estos los materiales más comunmente usados para la creación de este tipo de semiconductor debido a sus propiedades, se analizará su respuesta a distintas condiciones ambientales. Se basa en modelos físicos que consideran la generación y recombinación de portadores de carga, así como la influencia de la temperatura y la iluminación en la conductividad del material.

##  Fundamentos Teóricos
Los fotoresistores son dispositivos semiconductores cuya resistencia eléctrica varía en función de la intensidad luminosa que incide sobre ellos. Este comportamiento se debe a la generación de pares electrón-hueco cuando los fotones con suficiente energía impactan el material. En este proyecto, se modelan las siguientes ecuaciones fundamentales:

1. **Densidad intrínseca de portadores**:

```math
n_i = \sqrt{N_c N_v} e^{-E_g / (2 k_B T)}
```

   Donde:
   - $N_c$ y $N_v$ son las densidades de estados efectivos en la banda de conducción y valencia.
   - $E_g$ es la energía de banda prohibida del material.
   - $k_B$ es la constante de Boltzmann.
   - $T$ es la temperatura absoluta.

2. **Conductividad del material en oscuridad**:
   
```math
\sigma_{oscuridad} = q ( \mu_n n_0 + \mu_p p_0 )
```
   
   Donde:
   - $\mu_n$ y $\mu_p$ son las movilidades de electrones y huecos.
   - $n_0$ y $p_0$ son las concentraciones en equilibrio térmico.

3. **Generación de portadores debido a la iluminación**:
   
```math
\Delta n = \frac{\alpha I_0 e^{-\alpha x}}{h c / \lambda} \tau
```
   
   Donde:
   - $\alpha$ es el coeficiente de absorción del material.
   - $I_0$ es la intensidad luminosa incidente.
   - $\lambda$ es la longitud de onda de la luz incidente.
   - $\tau$ es el tiempo de vida medio de los portadores.

4. **Resistencia bajo iluminación**:

```math
R_{luz} = \frac{L}{\sigma_{luz} A}
```
   
   Donde $\sigma_{luz}$ es la conductividad con la luz incidente, $L$ es la longitud del fotoresistor y $A$ es el área.

## Características del Proyecto
- Simulación de la resistencia en oscuridad y bajo iluminación.
- Modelado basado en ecuaciones de semiconductores.
- Variación de resistencia con temperatura e intensidad luminosa.
- Gráficos de comportamiento con Matplotlib.
- Entrada interactiva para el usuario.
- Implementación flexible que permite modificar parámetros como el dopaje y la geometría del dispositivo.

## Estructura del Proyecto

┣ [fisica_de_semiconductores.py](./fisica_de_semiconductores.py)  # Código principal de simulación
┣ [README.md](./README.md)                     # Documentación del proyecto
┣ [fisica_de_semiconductores.exe](./fisica_de_semiconductores.exe)  # Ejecutable para Windows
┗ [Google Colab](https://colab.research.google.com/drive/1y6P3RH6G-NkssO_JAgaAo-BDssRLoYYJ?usp=sharing)  # Versión en la nube

## Instalación y Uso
Este proyecto ofrece dos formas sencillas de ejecutar la simulación: con un ejecutable listo para usar o mediante Google Colab.

### 1. Ejecutable (sin necesidad de instalar Python)

Descarga el ejecutable y ejecútalo:

[fisica_de_semiconductores.exe](./fisica_de_semiconductores.exe)

Al ejecutarlo, el programa pedirá los siguientes parámetros de entrada:

- Temperatura en °C (-30 a 80).
- Concentración de aceptores ($Na$) en cm⁻³.
- Concentración de donadores ($Nd$) en cm⁻³.
- Material del fotoresistor (CdS o CdSe).
- Área del fotoresistor en m² (1e-6 a 1e-4).
- Longitud del fotoresistor en m (1e-4 a 1e-2).
- Intensidad luminosa en lux (1 a 100).

Tras ingresar los datos, el programa calculará la resistencia en oscuridad y bajo iluminación, además de generar gráficos de variación de la resistencia con la temperatura y la iluminación.

### 2. Ejecución en Google Colab (sin necesidad de instalar nada)

Puedes ejecutar la simulación directamente en la nube sin instalar nada en tu computadora:

[Simulación de fotoresistor en Colab](https://colab.research.google.com/drive/1y6P3RH6G-NkssO_JAgaAo-BDssRLoYYJ?usp=sharing)

Al abrir el notebook en Google Colab, solo necesitas ejecutar las celdas en orden y seguir las instrucciones para ingresar los parámetros de simulación.
## Resultados
El programa generará dos gráficos:

1. **Resistencia en la oscuridad**: muestra la resistencia aproximada que tiene el dispositivo en la ausencia completa de luz.

1. **Variación de la resistencia con la temperatura**: muestra cómo cambia la resistencia en función de la temperatura en ausencia de luz.
2. **Variación de la resistencia con la iluminación**: representa la resistencia en función de la intensidad luminosa incidente.

La idea general de los resultados es simular en la medida de lo posible la hoja de datos que se podría conseguir del material creado con los parámetros ingresados.

## Tecnologías Usadas
- **Python 3**
- **NumPy** para cálculos numéricos.
- **Matplotlib** para visualización de datos.
- **PyInstaller** para la generación de ejecutables.

## Referencias
- Semiconductor physics and devices, **D.A. Neamen**, McGraw-Hill, 4ª ed.
- [CdSe - Wurtzite en PV Education](https://www.pveducation.org/pvcdrom/materials/cdse-wurtzite)
- [CdS en PV Education](https://www.pveducation.org/pvcdrom/materials/cds)
- [PV Education - Recursos generales](https://www.pveducation.org/pvcdrom/welcome-to-pvcdrom)




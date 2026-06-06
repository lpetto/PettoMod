# PETTOMOD

**Sistema de modulación asimétrica para AM por desplazamiento de offset matemático.**

No amplifica picos. No recorta señal. Solo desplaza la línea base.

---

## ¿Qué es Pettomod?

Pettomod es un método de modulación para transmisores de AM que logra altos índices de modulación positiva (hasta 390% en configuraciones de baja potencia) **sin distorsión añadida**. A diferencia de los sistemas analógicos que recortaban picos o amplificaban selectivamente, Pettomod desplaza matemáticamente el offset de la señal de audio. La forma de onda permanece idéntica; solo cambia su posición respecto al cero.

## ¿Cómo funciona?

El software de PC procesa el audio y aplica un offset negativo. La señal resultante (por ejemplo, una senoidal que originalmente oscilaba entre -1V y +1V pasa a oscilar entre -0.5V y +1.5V) se envía a un ESP32-S3 que genera PWM de 0 a 100% a 96 kHz. Este PWM excita un MOSFET que modula el GND de la etapa de RF.

## Componentes del sistema

- **PC**: Procesamiento de audio (filtros, compresor, ecualizador, pre-énfasis, y aplicación del offset)
- **ESP32-S3**: Placa de audio USB que genera PWM 0-100% y controla relés de antena y potencia
- **Etapa de RF**: Cualquier transmisor AM que acepte modulación por colector/drenador

## Potencias e índices de modulación

| Potencia | Modulación positiva alcanzable |
| :--- | :--- |
| 100W | 145% |
| 50W | 200% |
| 37.5W | 300% |
| 25W | 390% |

*Nota: Estos valores corresponden a una implementación con fuente de 49V. Pueden variar según el diseño del transmisor.*

---

## 📜 LICENCIA

Este proyecto se publica bajo **Creative Commons BY-NC-SA 4.0**.

**Usted es libre de:**
- Usar, modificar y compartir el proyecto para fines **no comerciales**
- Distribuir copias del software y la documentación

**Bajo las siguientes condiciones:**
- 👤 **Atribución** — Debe reconocer al autor original (este repositorio)
- 🚫 **No Comercial** — No puede usar este proyecto con fines comerciales
- 🔄 **Compartir Igual** — Si modifica el proyecto, debe publicarlo bajo la misma licencia

**⚠️ Para uso comercial (integración en productos vendidos, servicios de pago, etc.), se requiere autorización expresa del autor.**

El texto legal completo está disponible en [LICENSE](./LICENSE) y en [https://creativecommons.org/licenses/by-nc-sa/4.0/](https://creativecommons.org/licenses/by-nc-sa/4.0/)

---

## 👤 Autor

**Luis Angel Petitto**

- Proyecto publicado originalmente en: https://github.com/lpetto/PettoMod
- Contacto para consultas o solicitudes de licencia comercial: Lpetto@gmail.com

---

## 🤝 Agradecimientos

Este método está inspirado en los conceptos de *Asimod* y *Ultramodulación* utilizados por procesadores analógicos como el Frese Audio Pilot en las décadas de 1960-70, pero implementado con técnicas digitales modernas sin las limitaciones de aquellos sistemas.

---

## ⚠️ Nota legal

Este proyecto se comparte con fines educativos y experimentales. El usuario es responsable de cumplir con las regulaciones de radiodifusión de su país.

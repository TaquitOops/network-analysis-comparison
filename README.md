# Análisis Comparativo: Wireshark vs. tcpdump

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Category](https://img.shields.io/badge/Field-Cybersecurity-red)

##  Descripción del Proyecto
Este proyecto consiste en un análisis técnico comparativo entre dos de las herramientas de análisis de protocolos de red más utilizadas en la industria: **Wireshark** y **tcpdump**. El objetivo es identificar sus fortalezas, debilidades y escenarios de uso ideales para un Analista de Ciberseguridad.

##  Objetivos
- Investigar las funcionalidades principales de ambas herramientas.
- Diferenciar los casos de uso basados en la interfaz (GUI vs. CLI).
- Comprender la interoperabilidad a través de archivos de captura (.pcap).

##  Comparación Técnica

### Similitudes (Intersection)
1. **Código Abierto:** Ambas son herramientas gratuitas y de código abierto con gran soporte de la comunidad.
2. **Standard PCAP:** Ambas utilizan y soportan el formato de archivo `.pcap` para guardar y leer capturas de paquetes.
3. **Motor de Captura:** Ambas dependen de la biblioteca `libpcap` (Linux/macOS) o `WinPcap/Npcap` (Windows) para interactuar con la interfaz de red.

### Diferencias Clave

| Característica | Wireshark | tcpdump |
| :--- | :--- | :--- |
| **Interfaz** | Interfaz Gráfica de Usuario (GUI) rica y visual. | Interfaz de Línea de Comandos (CLI). |
| **Entorno de Uso** | Ideal para análisis profundo en estaciones de trabajo locales. | Ideal para servidores remotos, sistemas headless o bajo consumo de recursos. |
| **Visualización** | Análisis de flujos TCP y diagramas de secuencia visuales. | Salida de texto plano, requiere herramientas externas para visualización compleja. |
| **Consumo** | Alto consumo de memoria y CPU debido a la interfaz gráfica. | Muy ligero, diseñado para ejecutarse con un impacto mínimo en el sistema. |

---


##  Escenarios de Uso
- **Utilice Wireshark cuando:** Necesite inspeccionar visualmente una conversación TLS, seguir un flujo HTTP o realizar un análisis forense detallado tras un incidente.
- **Utilice tcpdump cuando:** Necesite capturar tráfico en un servidor Linux remoto vía SSH o cuando el sistema tenga recursos limitados.

##  Estructura del Repositorio
- `assets/`: Contiene el diagrama de Venn comparativo.
- `docs/`: Documentación extendida sobre el proceso de investigación.

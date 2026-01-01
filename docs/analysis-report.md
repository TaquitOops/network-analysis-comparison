# Informe Técnico: Análisis de Protocolos de Red

## 1. Introducción
Como analista de ciberseguridad, la capacidad de diseccionar el tráfico de red es vital. Este informe detalla las capacidades técnicas y limitaciones de Wireshark y tcpdump.

## 2. Respuestas al Análisis Técnico

### A. Acceso y Licenciamiento
* **Wireshark:** Software multiplataforma (Windows, macOS, Linux, Solaris). Es de código abierto bajo la licencia GNU GPL.
* **tcpdump:** Nativo de sistemas tipo Unix/Linux. Es de código abierto bajo una licencia estilo BSD.

### B. Interfaz de Usuario y Diseño
* **Wireshark:** Utiliza una interfaz gráfica rica. Organiza los paquetes en tres paneles: lista de paquetes, detalles del paquete y volcado en hexadecimal/ASCII. Utiliza colores para identificar protocolos (ej. rojo para errores TCP).
* **tcpdump:** Funciona enteramente en la terminal. La salida es flujo de texto que requiere un conocimiento sólido de los flags de comando para ser legible.

### C. Escenarios de Uso Recomendados
* **tcpdump:** Es el "primer respondedor". Se usa para capturas rápidas en servidores donde no hay interfaz gráfica o cuando el ancho de banda/recursos son limitados. Es ideal para dejarlo corriendo en segundo plano capturando tráfico sospechoso.
* **Wireshark:** Es la herramienta de "diagnóstico profundo". Se usa una vez que tenemos el archivo de captura para seguir flujos TCP, extraer archivos enviados por la red o analizar handshakes de cifrado.

### D. Gestión de Tráfico y Filtrado
* **Filtrado de Captura:** Ambos pueden usar filtros BPF (Berkeley Packet Filter). Ejemplo: `tcp port 80`.
* **Filtrado de Visualización:** Wireshark sobresale aquí, permitiendo filtros complejos post-captura (ej. `http.request.method == "POST"`) sin necesidad de volver a capturar los datos.

## 3. Limitaciones y Consideraciones
1.  **Seguridad:** Ejecutar Wireshark como root/admin puede ser un riesgo de seguridad debido a la complejidad de sus dissectores. Se recomienda capturar con tcpdump (privilegios limitados) y analizar con Wireshark (usuario normal).
2.  **Rendimiento:** En redes de 10Gbps, Wireshark puede perder paquetes al intentar procesarlos gráficamente. tcpdump es mucho más robusto para capturas de alta velocidad.

## 4. Conclusión
No se trata de elegir una herramienta sobre la otra, sino de entender su interoperabilidad. Un flujo de trabajo profesional implica capturar con la ligereza de **tcpdump** y diseccionar con la potencia visual de **Wireshark**.

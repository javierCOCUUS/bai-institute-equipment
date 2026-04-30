# Justificación Técnica: Ecosistema de Control Basado en Mesa 7i95 y LinuxCNC

## Introducción
Para la propuesta técnica del **Building Architecture Institute (BAI)**, se ha seleccionado una arquitectura de control abierta, robusta y de alto rendimiento. La estandarización en torno a las placas de control **Mesa 7i95** y el software **LinuxCNC** garantiza una interoperabilidad total entre las diferentes máquinas (Fresadoras CNC y Láseres CO₂), facilitando el mantenimiento, la escalabilidad y la formación del personal técnico.

## 1. El Ecosistema de Control: Placas Mesa (FPGA Ethernet)
La elección de hardware **Mesa** (como la **7i95**, **7i76E** o la potente **7i80HD**) representa el estándar de facto para el control de máquinas de alto rendimiento bajo LinuxCNC.

### Variantes y Capacidades:
- **Mesa 7i95**: Ideal para sistemas de hasta 6 ejes paso a paso (step/dir) con gran densidad de E/S.
- **Mesa 7i76E**: Muy popular en máquinas de madera por su combinación de control de motores, entradas/salidas analógicas para variadores de frecuencia (VFD) y robustez.
- **Mesa 7i80HD / 7i92**: Placas de alto rendimiento con capacidad de expansión masiva mediante tarjetas "hija" (daughtercards), permitiendo controlar máquinas con docenas de señales de E/S, sistemas de cambio de herramienta complejos y múltiples cabezales.

### Ventajas Clave del Ecosistema:
- **Procesamiento en FPGA**: La generación de pulsos y el conteo de encoders se realiza a nivel de hardware, liberando al procesador del PC y permitiendo frecuencias ultra-estables de hasta **4-8 MHz**.
- **Conectividad Ethernet Industrial**: Garantiza inmunidad al ruido y facilidad de integración en redes de taller.

## 2. Software de Control: LinuxCNC
**LinuxCNC** es el estándar de oro en software de control de código abierto para máquinas herramienta, utilizado desde pequeños talleres hasta centros de mecanizado industriales.

### Virtudes del Ecosistema LinuxCNC:
- **Control en Tiempo Real**: Al ejecutarse sobre un kernel Linux con parches de tiempo real (RT_PREEMPT), garantiza que las señales de control se envíen con una latencia mínima y determinista, algo vital para la precisión en el corte y el grabado.
- **HAL (Hardware Abstraction Layer)**: Permite configurar y "cablear" virtualmente cualquier componente de la máquina mediante software. Podemos adaptar la misma lógica de control tanto para una fresadora de gran formato como para un láser CO₂.
- **Sin Dependencia de Proveedor**: El BAI no quedará atado a licencias propietarias anuales o a hardware cerrado que quede obsoleto. El sistema es totalmente auditable y modificable.
- **Cinemática Avanzada**: LinuxCNC maneja nativamente cinemáticas complejas, lo que facilita el control de la **CNC de 5 ejes** con una precisión superior en el seguimiento de trayectorias G-code.

## 3. Integración con Estándares de Arquitectura: Soporte BTLx
Una de las mayores ventajas de utilizar LinuxCNC junto con hardware de alto rendimiento es la capacidad de manejar formatos avanzados como **BTLx** (Building Timber Language XML).

### ¿Qué es BTLx y por qué es vital para el BAI?
El **BTLx** es el estándar internacional de intercambio de datos para la construcción en madera (Timber Construction). A diferencia del G-code convencional (que solo describe movimientos de herramienta), el BTLx describe **operaciones arquitectónicas** (como ensambles de cola de milano, muescas, taladros y cortes de sierra complejos).

- **Continuidad Digital**: Permite que los diseños realizados en software BIM especializado (como Cadwork, Dietrich's o SEMA) se transfieran directamente a la máquina sin pérdida de información geométrica.
- **Automatización de Procesos**: Al usar LinuxCNC, se pueden desarrollar intérpretes personalizados que traduzcan estas operaciones complejas de BTLx directamente en trayectorias de herramienta optimizadas para la CNC de 5 ejes.
- **Precisión Estructural**: El soporte de este formato asegura que el BAI pueda fabricar estructuras de madera de gran formato con una precisión milimétrica, algo fundamental para la arquitectura moderna sostenible.

## 4. Unificación: De la Fresadora al Láser
El uso de la Mesa 7i95 en los **láseres CO₂** permite un control ultra-preciso de la potencia mediante PWM (Modulación por Ancho de Pulsos) sincronizado con el movimiento. Esto elimina el efecto de "quemado" en las esquinas y permite grabados con una escala de grises mucho más fina que los controladores comerciales cerrados.

### Resumen de Beneficios para el BAI:
1. **Curva de Aprendizaje Unificada**: El personal técnico solo necesita aprender una interfaz y un sistema de configuración.
2. **Repuestos Simplificados**: Al usar la misma placa en múltiples máquinas, el stock de repuestos se reduce drásticamente.
3. **Potencial de Innovación**: Al ser un sistema abierto, el BAI puede implementar sus propios macros de G-code para procesos experimentales de arquitectura y fabricación digital.

---
*Documento preparado para la propuesta técnica de maquinaria - Building Architecture Institute.*

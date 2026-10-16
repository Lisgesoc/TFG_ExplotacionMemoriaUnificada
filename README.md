# TFG: Explotación Arquitectura Memoria Unificada
Proyecto de benchmarking de sistemas con arquitecturas de memoria unificada basada en aceleradores. Comparación de rendimientos con sistemas sin dicha arquitectura.

## Sistema
- Nombre: DGX Spark GB10
- Vendedor: NVIDIA
- CPU: Grace
- GPU: Blackwell
- RAM: 128GB LPDDR5
- Sistema Operativo: DGX OS (Basado en Linux: Ubuntu)

## Entorno
- Conexión remota por SSH
- VS CODE
- C/C++, CUDA y Python

## Algoritmos
- Debemos probar algoritmos con mucha carga de transacciones de memoria entre CPU y GPU
- Posibles ámbitos: Machin Learning, Procesamiento gráfico, Simulaciones
- Deben tener la misma base de computo pero estar adaptados a cada arquitectura de prueba.

## Teoría
Los sistemas de arquitectura de memoria unificada entre la CPU y sus aceleradores optimizan el computo de gran manera. El uso de la misma memoria reduce las transacciones a 0 y teniendo en cuenta que la memoria siempre ocupa gran parte de la latencia a la hora de la ejecución de un programa mejora su rendimiento. De hecho ya no solo a nivel hardware sino a nivel software pues permite una programación mas eficiente para resolver los mismos problemas necesitando un menor numero de lineas de código para el diseño de las soluciones. A pesar de esto no todo es positivo pues también acarrea una mayor carga de trabajo para el sistema operativo debiendo mantener la coherencia de datos y accesos a memoria de dos o más unidades de procesamiento. Además el bus de acceso a memoria, que en el caso del sistema a mi alcance es el NVLink, debe administrar la comunicación entre varios dispositivos solicitantes.

## Otros Sistemas
- Play Station 5
- Sistemas Apple con CPU familia Apple Silicon

## Ideas
### Para poder medir realmente la mejoría de la arquitectura UMA deberemos obtener ratios base de mejoría debido a:
- La potencia de computo base de sus unidades de procesamiento, la GPU Blackwell es mucho más capaz que la mayoría de GPUs. Solución: ejecución de código sin transferencias únicamente computo y sacar ratio de mejoria.
- La cantidad de memoria a disposición, las tareas que requieran mucha memoria provocaran mas fallos en un sistema que tenga menos GB para CPU y para GPU. Solución: ejecución de algoritmos que no excedan las limitaciones de memoria.
  

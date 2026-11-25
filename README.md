# Optimización Financiera y Operativa de Auto Spa de la 57

Proyecto integrador de Ingeniería de Datos e Inteligencia Artificial (Universidad Santo Tomás, Seccional Tunja) que articula infraestructura de redes multisede, procesamiento paralelo/distribuido y analítica visual para **Auto Spa de la 57**.

## Integrantes
* **Juan Pablo Montañez Chaparro** — Arquitectura de Red (Cisco Packet Tracer) e Integración
* **Juan Sebastián Molina Araque** — Procesamiento Paralelo y Distribuido (`multiprocessing` y `PySpark`)
* **Jaime Martínez Palencia** — Limpieza de Datos y Analítica Exploratoria (Python)
* **Marlon Diaz** — Modelado de Datos y Tablero Ejecutivo (Microsoft Power BI)

## Estructura del Repositorio
* `1_Redes_PacketTracer/`: Archivo `.pkt` con la topología de 3 routers (`sede tunja`, `sede 2`, `datacenter`), direccionamiento VLSM (`192.168.10.0/24`), VLANs 802.1Q (`OPERACION` y `ADMIN`) y enrutamiento OSPFv2.
* `2_Computacion_Paralela_Spark/`: Cuadernos `.ipynb` con la ingesta paralela en Python (`multiprocessing.Pool`) sobre 334 hojas diarias (10,990 registros) y agregaciones distribuidas en `PySpark` sobre 150,000 registros.
* `3_Analitica_Visualizacion/`: Scripts de análisis exploratorio (`Matplotlib`/`Seaborn`), datasets anonimizados y archivo `.pbix` del tablero interactivo en Power BI.

## Instrucciones de Ejecución

### 1. Simulación de Red (`1_Redes_PacketTracer`)
1. Abrir **Cisco Packet Tracer** (versión 8.2 o superior).
2. Cargar el archivo `.pkt` ubicado en `1_Redes_PacketTracer/`.
3. Verificar adyacencias OSPF (`show ip ospf neighbor`) y ejecutar pruebas `ping` desde `Operación tunja` (`192.168.10.2`) hacia `192.168.10.34` y `192.168.10.89`.

### 2. Flujo ETL Paralelo y Apache Spark (`2_Computacion_Paralela_Spark`)
1. Abrir los cuadernos `.ipynb` en **Google Colab** o Jupyter Notebook.
2. Instalar dependencias si se ejecuta en local:
   ```bash
   pip install pyspark pandas openpyxl

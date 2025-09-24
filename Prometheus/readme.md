# 2. Instalación de Prometheus y Node Exporter

Para el monitoreo de la infraestructura de nuestro servidor EC2, se implementó Prometheus junto con Node Exporter. Prometheus se encarga de recolectar y almacenar las métricas como una base de datos de series temporales, mientras que Node Exporter expone las métricas del hardware y del sistema operativo del host.

## 2.1 Instalación

Se optó por el método de instalación a través del gestor de paquetes apt de Ubuntu 20.04, ya que proporciona una configuración inicial robusta y simplifica la gestión del servicio.

- Primero, se actualizaron los repositorios de paquetes del sistema.
<img width="715" height="290" alt="image" src="https://github.com/user-attachments/assets/788a4d6a-d328-4014-9e03-d6d1afd16ce6" />

- A continuación, se instalaron ambos paquetes con un solo comando.
<img width="757" height="136" alt="image" src="https://github.com/user-attachments/assets/62683b9b-012b-4bb2-9ee2-6e2d0af087c5" />

- Este proceso instala los binarios, crea los archivos de configuración por defecto y configura los servicios systemd para que se ejecuten automáticamente al iniciar el sistema.

## 2.2 Verificación de los Servicios

Una vez finalizada la instalación, se verificó que ambos servicios estuvieran activos y funcionando correctamente utilizando `systemctl`.
<img width="871" height="409" alt="image" src="https://github.com/user-attachments/assets/09b07601-2a8e-4d30-973a-232b51b16971" />
<img width="880" height="396" alt="image" src="https://github.com/user-attachments/assets/ef6817fe-7113-4394-8d96-f0e6b67a8bcd" />

## 2.3 Configuración y Targets

La instalación a través de apt genera automáticamente un archivo de configuración en `/etc/prometheus/prometheus.yml`. Este archivo ya viene preconfigurado para que Prometheus se monitoree a sí mismo y para que recolecte las métricas expuestas por Node Exporter en `localhost:9100`.
<img width="863" height="735" alt="image" src="https://github.com/user-attachments/assets/45671d70-9c7e-4bc5-88e6-853487d500d4" />

## 2.4 Acceso a la Interfaz Web y Consulta

Para la prueba final, se accedió a la interfaz web de Prometheus a través de la IP pública de la instancia EC2.

- Dentro de la interfaz, en la sección **Status → Targets**, se pudo verificar que tanto el endpoint de Prometheus como el de Node Exporter estaban en estado UP, indicando que la recolección de métricas estaba funcionando.
<img width="953" height="524" alt="image" src="https://github.com/user-attachments/assets/ba9471bf-f2b2-4d5b-9beb-b8a005a652ba" />

- Como parte de la actividad, se ejecutó una consulta simple con la métrica `up` en la pestaña **Graph**. El resultado mostró un valor de 1 para ambos jobs, confirmando que los servicios están activos y son accesibles para Prometheus.
<img width="948" height="439" alt="image" src="https://github.com/user-attachments/assets/0e30f268-82a5-41ef-8af9-9eee163e5841" />


**Autor**: Aaron Casildo Rubalcava  
**Institución**: TECNM / Instituto Tecnológico de Tijuana  
**Materia**: Sistemas Programables  
**Año**: 2025

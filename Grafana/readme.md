# 3. Instalación y Configuración de Grafana

En esta fase se despliega Grafana, la plataforma de visualización que unificará las métricas de InfluxDB y Prometheus en dashboards interactivos.

## 3.1 Preparación del Sistema

Se instalan las dependencias necesarias para gestionar los repositorios de software de forma segura.
<img width="942" height="137" alt="image" src="https://github.com/user-attachments/assets/d5e2aeb8-3581-4a5e-b6f1-44da23ec8989" />

## 3.2 Agregar el Repositorio de Grafana

Se importa la clave GPG de Grafana y se agrega su repositorio oficial al sistema. Este método utiliza `signed-by` para mayor seguridad, que es la práctica recomendada actualmente.
<img width="858" height="122" alt="image" src="https://github.com/user-attachments/assets/44c3b6d7-bdc6-4199-ac0c-2b28b6601b3c" />

## 3.3 Instalar Grafana

Con el repositorio ya configurado, se actualiza la lista de paquetes para incluir los de Grafana y se procede con la instalación.
<img width="709" height="306" alt="image" src="https://github.com/user-attachments/assets/7d229ffc-e4e9-4388-9628-377c8793e276" />

## 3.4 Iniciar y Verificar el Servicio

Se inicia el servicio de Grafana y se habilita para que se ejecute automáticamente cada vez que el servidor se reinicie.
<img width="1195" height="465" alt="image" src="https://github.com/user-attachments/assets/98f48fda-4453-47df-a0b3-9d69b0e7337a" />

Se debe observar un estado de `active (running)`, lo que confirma que Grafana está funcionando correctamente.

## 3.5 Acceso a la Interfaz Web

Se accede a la interfaz de Grafana a través de un navegador.

- URL: `http://<IP_PUBLICA_EC2>:3000`
- Usuario por defecto: `admin`
- Contraseña por defecto: `admin`
<img width="1898" height="762" alt="image" src="https://github.com/user-attachments/assets/665412bf-b316-4e2b-b1e5-728cfabe47a8" />

Al iniciar sesión por primera vez, Grafana solicitará de inmediato el cambio de la contraseña por defecto por una nueva y segura.
<img width="1910" height="769" alt="image" src="https://github.com/user-attachments/assets/7464b959-f2ec-4651-af2d-8e4f0494c815" />

<img width="1901" height="878" alt="image" src="https://github.com/user-attachments/assets/42e17eed-a3f3-49be-9c53-394d23a8e896" />


## Grafana - Data Sources

Se configura la fuente de datos para conectar Grafana con InfluxDB y Prometheus, permitiendo la visualización de métricas en dashboards interactivos.

**Autor**: Aaron Casildo Rubalcava  
**Institución**: TECNM / Instituto Tecnológico de Tijuana  
**Materia**: Sistemas Programables  
**Año**: 2025

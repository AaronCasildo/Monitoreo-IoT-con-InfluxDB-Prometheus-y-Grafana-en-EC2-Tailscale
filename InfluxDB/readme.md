# 1. Instalación y Configuración de InfluxDB  
En esta sección se explica el procedimiento para instalar y configurar InfluxDB v2 como base de datos de series temporales destinada al almacenamiento de datos provenientes de sensores IoT.  

## 1.1 Instalación del Paquete  
- La instalación se llevó a cabo en un servidor con Ubuntu 20.04. Primero se añadió la clave GPG y el repositorio oficial de InfluxData al gestor de paquetes apt.  
<img width="1691" height="138" alt="image" src="https://github.com/user-attachments/assets/0a540bae-a21e-4d18-b6b9-f1a98aceec30" />
- Una vez agregado el repositorio, se actualizó la lista de paquetes y posteriormente se instaló InfluxDB.
<img width="945" height="564" alt="image" src="https://github.com/user-attachments/assets/391081fe-0b8e-407d-9c71-dbdbbd149d19" />


## 1.2 Configuración Inicial (influx setup)  
- Tras la instalación, se ejecutó el comando **influx setup** para inicializar la base de datos. Este asistente permitió crear el primer usuario, una organización y un bucket.  
- Los parámetros empleados fueron los siguientes:  
  - Username: Aaron Casildo Rubalcava  
  - Organization: SistemasProgramables  
  - Bucket: datos  
  - Retention: infinite (0)
  <img width="626" height="298" alt="image" src="https://github.com/user-attachments/assets/cdedc205-bd06-4aa5-ad7c-0984b3700c77" />


## 1.3 Obtención del API Token  
- Durante la configuración inicial se generó el token de administrador, necesario para interactuar con la API de InfluxDB.  
- Dicho token se obtuvo ejecutando el comando **influx auth list**.
<img width="1892" height="133" alt="image" src="https://github.com/user-attachments/assets/1d42ca1d-a612-476f-9ce3-622a2bf7bdb0" />


## 1.4 Verificación del Servicio  
- Para comprobar que InfluxDB se estuviera ejecutando de forma correcta, se verificó el estado del servicio con el comando **systemctl**.  
- El resultado mostró que el servicio estaba activo (running), confirmando que la base de datos estaba operativa.
<img width="865" height="431" alt="image" src="https://github.com/user-attachments/assets/75a353c6-defc-4754-92e6-fd1198b2ebdf" />


## 1.5 Consulta Simple desde la CLI  
- Con el fin de validar la correcta creación de los recursos, se ejecutó una consulta sencilla desde la línea de comandos para listar los buckets disponibles.  
- Entre los resultados se encontró el bucket **datos** creado, además de los buckets internos del sistema.  
<img width="1061" height="107" alt="image" src="https://github.com/user-attachments/assets/321f3a10-71cf-48e7-99b7-44fc6313b65e" />


## 1.6 Acceso a la Interfaz Web (UI)  
- Finalmente, se comprobó el acceso a la interfaz gráfica de InfluxDB a través del navegador, ingresando la dirección IP de la instancia EC2 junto con el puerto 8086.  
- La página de inicio de sesión se cargó correctamente, permitiendo acceder con las credenciales creadas durante la configuración inicial.  
<img width="774" height="126" alt="image" src="https://github.com/user-attachments/assets/a927a984-39c7-402c-b71c-9929d8c5ac3b" />
<img width="1905" height="826" alt="image" src="https://github.com/user-attachments/assets/9e14113a-aeb5-47e5-8697-cf7ef1ea20c5" />
<img width="1920" height="989" alt="image" src="https://github.com/user-attachments/assets/668325fe-5b42-46ab-a2c6-9d2f21f0c48d" />

---

**Autor**: Aaron Casildo Rubalcava  
**Institución**: TECNM / Instituto Tecnológico de Tijuana  
**Materia**: Sistemas Programables  
**Año**: 2025  

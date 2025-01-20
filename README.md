# **Desafío 4: Configuración de AWS CLI y S3**

Este proyecto detalla los pasos para configurar AWS CLI, crear un bucket en S3 y gestionar permisos utilizando roles y políticas de IAM.

## **1. Instalación de `aws-shell`**
Antes de comenzar, asegúrate de tener instalado **Python**. Luego, instala `aws-shell` usando:
```bash
pip install aws-shell

Una vez instalado acceder con: `aws-shell`
```

## **2. Configuracion de credenciales en AWS CLI**
- Ingresar a la consola de **AWS** y acceder al servicio IAM -> **Create user**

![image](https://github.com/user-attachments/assets/ff524d87-43e8-421b-91b6-fcdbe539f4b2)

- Ingresar un **nombre** para el usuario

![image](https://github.com/user-attachments/assets/3acb52f3-2484-47c2-9e65-415697a1db38)

- Seleccionar **Attach policies directly**

![image](https://github.com/user-attachments/assets/ac954f22-e08a-41f0-923c-3343aec606cc)

- Buscar y seleccionar **AdministratorAccess**

![image](https://github.com/user-attachments/assets/603082bd-db40-4972-988c-f065820b8b6e)

![image](https://github.com/user-attachments/assets/bf96d0be-96dd-4681-8808-d61403ee6cb4)

- Seleccionar el usuario creado y elegir **Create access key**

![image](https://github.com/user-attachments/assets/c5f6a929-32a0-4b96-bdcd-1f0e1c337f65)

- Asignarle **Command Line Interface (CLI)**

![image](https://github.com/user-attachments/assets/411fe03f-4a9a-417c-86a7-fc0ffe8c89a0)

- Finalizar el proceso y descargar las credenciales .csv

![image](https://github.com/user-attachments/assets/c96376a2-473a-479e-b46d-4549637a3d0f)

## **3. Configuracion de CLI de AWS

- Abrir una ventana de CMD y escribir el comando `aws-shell`
- Configura el CLI con el Usuario Administrador con el comando `configure`





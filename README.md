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

## **3. Configuracion de CLI de AWS**

- Abrir una ventana de CMD y escribir el comando `aws-shell`
- Configurar el CLI con el Usuario Administrador con el comando `configure`
  
![image](https://github.com/user-attachments/assets/2480c37f-bcc4-45b3-aa13-17970749c68d)

- Verificar las credenciales configuradas

![image](https://github.com/user-attachments/assets/cee6dc4a-2e56-4615-8fb3-0f790237deee)

## **4. Creacion del Bucket S3**

![image](https://github.com/user-attachments/assets/7255c44b-109d-4f7c-b886-09c947617084)

**Verificacion del bucket creado**

![image](https://github.com/user-attachments/assets/116ef938-09ed-412c-8f42-0696ff214ec0)

## **5. Creacion de rol y politica**

- Crear un rol con permisos para **escribir**
```bash
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowRolePutObject",
      "Effect": "Allow",
      "Action": "s3:PutObject",
      "Resource": "arn:aws:s3:::educacionitbucket-cli/*"
    }
  ]
}
```

- Crear la política para **asumir** el rol

```bash
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::626635449201:user/s3-support"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```
- Crear el rol

![image](https://github.com/user-attachments/assets/5c605228-cf40-4680-b0b5-eb7c367aef04)

- Adjuntar la política al rol

![image](https://github.com/user-attachments/assets/6f3c07b1-f920-4c04-9913-30b18bede42b)

- Verificar el rol

![image](https://github.com/user-attachments/assets/0b7378ec-0c79-4ff2-ad89-200121ff3b46)

## **6. Creacion de usuario IAM s3-support**

![image](https://github.com/user-attachments/assets/1ad3a824-125c-4924-aeff-eb7cb664f7c2)

- Crear **credenciales programáticas** para el usuario 

![image](https://github.com/user-attachments/assets/2b291e90-a3b3-44cc-943f-8430a8f8c8f6)


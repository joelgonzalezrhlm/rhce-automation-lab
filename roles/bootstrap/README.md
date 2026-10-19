# Rol bootstrap

## Objetivo

Preparar el acceso administrativo inicial a los servidores Linux de la infraestructura, creando el usuario de automatización, configurando sus privilegios y gestionando su clave pública SSH.

## Responsabilidades

- Comprobar que el sistema operativo pertenece a la familia RedHat.
- Instalar el paquete sudo.
- Crear el usuario de administración de Ansible.
- Añadir el usuario al grupo administrativo configurado.
- Configurar los privilegios sudo con o sin contraseña.
- Instalar la clave pública SSH cuando esté habilitado.
- Validar la configuración de sudo antes de aplicarla.

## Variables principales

| Variable | Valor predeterminado | Descripción |
|---|---|---|
| user_account | ansible | Usuario de administración |
| ssh_manage_key | true | Habilita la gestión de claves SSH |
| ssh_public_key | "" | Ruta de la clave pública en el controlador |
| sudo_nopasswd | true | Permite sudo sin contraseña |
| manage_sudo_group | true | Habilita la gestión del grupo administrativo |
| sudo_group | wheel | Grupo administrativo |
| base_os_supported | RedHat | Familia de sistema operativo admitida |

## Requisitos

- Ansible instalado en el controlador.
- Acceso SSH inicial a los nodos.
- Privilegios suficientes para administrar el sistema.
- Sistemas de la familia RedHat compatibles con el rol.
- Archivo de clave pública disponible en el controlador si se habilita su instalación.

## Ejecución

```bash
ansible-playbook -i inventory/hosts.yml playbooks/bootstrap.yml

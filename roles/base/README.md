
# Rol base

## Objetivo

Aplicar la configuración mínima común a los servidores
Linux de la infraestructura.

## Responsabilidades

- Configurar el hostname.
- Instalar paquetes comunes.
- Instalar y gestionar chronyd.
- Comprobar el sistema operativo mediante facts.
- Verificar el estado del servicio y consultar la sincronización.

## Variables principales

| Variable | Valor predeterminado | Descripción |
|---|---|---|
| base_hostname | inventory_hostname | Hostname esperado |
| base_common_packages | vim-enhanced, curl, wget, bash-completion | Paquetes comunes |
| base_time_sync_package | chrony | Paquete horario |
| base_time_sync_service | chronyd | Servicio horario |

## Requisitos

- Ansible instalado en el controlador.
- Acceso SSH a los nodos.
- Privilegios para administrar el sistema.
- Sistemas de la familia RedHat compatibles con el rol.

## Ejecución

```bash
ansible-playbook -i inventory/hosts.yml playbooks/site.yml
```

## Idempotencia

Ejecutar el playbook dos veces consecutivas y comprobar
que la segunda ejecución no introduce cambios innecesarios.


### Problema a acceder a carpeta compartida:
* Win + r -> gpedit.msc
* Ir a Configuración del equipo -> Plantillas administrativas -> Red -> Estación de trabajo Lanman -> Habilitar inicios de sesion de invitados no seguros
* Dar Habilitar, Aplicar y Aceptar
* En caso de que el problema siga:
> Entrar al editor de registros (regedit)
> Cambiar el valor de AllowInsecureGuestAuth a 1
>> ruta: [HKEY_LOCAL_MACHINE/SYSTEM/CurrentControlSet/Services/LanmanWorkstation/Parameters]
>> "AllowInsecureGuestAuth"=dword:1

# REFLEX EGG FOR PTERODACTYL
[![Reflex](https://img.shields.io/badge/Reflex-WEB-5646ED?style=for-the-badge&logo=reflex&logoColor=white&labelColor=101010)](https://reflex.dev) ➡️
[![Pterodactyl](https://img.shields.io/badge/Pterodactyl-logic&static-blue?style=for-the-badge&logo=pterodactyl&logoColor=white&labelColor=101010)](https://pterodactyl.io/)

## EGG de REFLEX
Creado para poder utilizar [Pterodactyl](https://pterodactyl.io/) como host de las aplicaciones 
realizadas con [Reflex](https://reflex.dev/) tanto la parte estática como la lógica.

## USO:
 - Con Pterodactyl ya instalado... [*Documentación Instalación*](https://pterodactyl.io/panel/1.0/getting_started.html)
   debes Importar en la sección Nest>Eggs este nuevo egg.

 - Ahora debes crear una nueva instancia a partir del Egg configurando todas las variables:
   > ![image](https://github.com/Cocotterooo/docker-pterodactyl-reflex/assets/103317717/cef3b53a-8226-415e-b5b6-871ba74c30e4)
 - Una vez Inicies la instancia, se deberá clonar el repositorio de tu app, en la raíz, si tienes variables de entorno
   crea tu archivo .env correspondiente.
> [!CAUTION]
> Nunca edites ningún archivo de tu app dentro del contenedor, exceptuando tu archivo **.env**, si lo
> haces... en la próxima actualización del repositorio de tu app, tendrás que reinstalar la instancia

## Compatibilidad:
- La intancia de Pterodactyl debe tener 2 puertos disponibles, (por defecto 3000:front y 8000:back)
- Estructura de tu proyecto:
```
Repository
  ├── README.md **
  ├── LICENSE.txt **
  ├── .github
  ├── venv 
  ├── .env
  └── app_name
      ├── requirements.txt
      ├── .web
      ├── assets
      ├── app_name
      │     ├── __init__.py
      │     └── app_name.py
      └── rxconfig.py
      
(optional: **)
```

> [!Note]
> No es necesario tener dispuesto así el proyecto en tu entorno local, puedes cambiar el lugar del **entorno virtual**
> o el arvhivo **.env** si lo prefieres... **pero en Pterodactyl debe estar así dispuesto.**

## FUNCIONAMIENTO:
- [x] Al instalar la instancia se utilizará una imagen docker que incluirá Python 3.12 y el paquete unzip ya que lo
      requiere Reflex durante las inicializaciones.
- [x] Al iniciar por primera vez o sin existir el archivo **.git** intentará clonar tu repositorio en primer nivel, después
      creará un entorno virtual, instalará los paquetes necesarios para el funcionamiento de tu app si están listados 
      en tu archivo de **"requirements"** (entre ellos tu versión de reflex). Una vez esté completada la instalación
      intentará hacer un `reflex init` de tu app y posteriormente intentará desplegarla en producción con
      `reflex run --env prod --loglevel debug` lo que implica que desplegará tanto el Frontend como también el Backend de tu aplicación.
- [x] ¡Y listo! ¡Ya tienes funcionando en Pterocatyl tu aplicación de Reflex 😯🌟!
  

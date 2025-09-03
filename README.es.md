<!-- hide -->
#  Políticas de Seguridad DLP

> By [@rosinni](https://github.com/rosinni) and [other contributors](https://github.com/breatheco-de/data-loss-prevention-dlp-project/graphs/contributors) at [4Geeks Academy](https://4geeksacademy.co/)

[![build by developers](https://img.shields.io/badge/build_by-Developers-blue)](https://4geeks.com)
[![build by developers](https://img.shields.io/twitter/follow/4geeksacademy?style=social&logo=twitter)](https://twitter.com/4geeksacademy)

*Estas instrucciones estan [disponibles en español](https://github.com/breatheco-de/data-loss-prevention-dlp-project/blob/main/README.es.md)*

### Antes de empezar...

> ¡Te necesitamos! Estos ejercicios se crean y mantienen en colaboración con personas como tú. Si encuentras algún error o falta de ortografía, contribuye y/o repórtalo.

<!-- endhide -->

## 📖 Propósito del Proyecto

Este proyecto educativo de ciberseguridad se enfoca en la creación e implementación de políticas de seguridad para la **Prevención de Pérdida de Datos (DLP)** dentro de una organización. Los estudiantes aprenderán a aplicar el principio del menor privilegio y asegurar que solo el personal autorizado tenga acceso a datos sensibles a través de ejercicios prácticos.

### 🎯 Objetivos de Aprendizaje:
- **Parte 1**: Definir y establecer políticas de DLP integrales que ayuden a proteger la información confidencial
- **Parte 2**: Implementar medidas técnicas específicas, como la **restricción del acceso a dispositivos USB**, para asegurar que las políticas de DLP se apliquen efectivamente en la práctica

## 🛠️ Tecnologías Utilizadas

Este proyecto utiliza las siguientes tecnologías y herramientas:

- **Sistema Operativo**: Windows (se recomienda Máquina Virtual)
- **Virtualización**: VirtualBox con Extension Pack
- **Gestión de Políticas**: Editor de Políticas de Grupo de Windows (`gpedit.msc`)
- **Marco de Seguridad**: Principios de Prevención de Pérdida de Datos (DLP)
- **Documentación**: Informes PDF y documentación de políticas
- **Entorno de Pruebas**: Gestión de cuentas de usuario de Windows
- **Dispositivos de Almacenamiento**: Dispositivos USB para pruebas de restricción

## 🚀 Requisitos Previos e Instalación

### Requisitos del Sistema:
- Máquina virtual Windows (Windows 10/11 recomendado)
- VirtualBox con Extension Pack instalado
- Privilegios administrativos en la VM
- Dispositivo USB para probar las restricciones

### 🌱 ¿Cómo empezar este proyecto?

## 📝 Instrucciones

### Creación de Políticas de Seguridad DLP

1. **Introduccion al Data Loss Prevention.** Redacta una introducción al DLP,explicando el concepto general de DLP y su importancia dentro de una organización, destacando su papel en la protección de datos confidenciales.
2. **Clasificación de datos.** Define cómo la organización clasificará los datos en función de su sensibilidad Establece al menos tres categorías de clasificación, por ejemplo:
    - **Datos Públicos**
    - **Datos Internos**
    - **Datos Sensibles**

3. **Acceso y Control.** Aplicando el **principio del menor privilegio**, establece políticas de acceso basadas en el **principio del menor privilegio** y define el flujo de revisión de permisos, indicando qué roles dentro de la organización serán responsables de estas revisiones y cómo se llevarán a cabo.
4. **Monitoreo y Auditoría.** Establece reglas para el monitoreo de datos sensibles y la auditoría de actividades relacionadas con esos datos. Describe más detalladamente las herramientas de monitoreo y auditoría que se utilizarán (por ejemplo, soluciones SIEM o DLP específicas para monitorear el uso de datos). 
5. **Prevención de Filtraciones.** Define cómo se evitará la filtración de datos sensibles, utilizando tecnologías como el cifrado y herramientas de DLP.
6. **Educación y concientización.** Describe cómo se capacitará al personal sobre las políticas de seguridad y los riesgos asociados.

### 📁 Ejemplo de Informe de Caso Real

Para una ilustración práctica, consulta el [Caso de Estudio de Prevención de Pérdida de Datos](assets/security-policies.pdf). Este ejemplo está enfocado en el uso de **Google Drive**, pero puedes adaptarlo a cualquier sistema de almacenamiento o colaboración basado en la nube o local. La clave es garantizar que solo los usuarios autorizados accedan a la información según lo necesiten para realizar su trabajo, respetando siempre el **Principio del Menor Privilegio**.


## Implementación de Políticas de Restricción de Dispositivos USB

La segunda parte de este ejercicio consiste en la implementación de políticas de restricción del uso de **dispositivos USB**. Estas restricciones son esenciales para evitar la filtración de datos confidenciales por medio de dispositivos de almacenamiento removibles. Esta política está directamente vinculada a las políticas de DLP creadas en la primera parte del ejercicio.

> 💡 La siguiente practica estará enfocada en una maquina virtual windows.


### 📋 Instrucciones de Configuración

#### Paso 1: Configuración de la Máquina Virtual
Antes de implementar las políticas de DLP, asegúrate de que tu entorno virtual esté configurado correctamente:

> ⚠️ **Importante**: Para aplicar restricciones de dispositivos USB, tu VM debe poder acceder a los dispositivos USB conectados a tu máquina física (host).

1. **Instalar VirtualBox Extension Pack**
   - Visita el [sitio oficial de VirtualBox](https://www.virtualbox.org/wiki/Downloads)
   - Descarga el Extension Pack que coincida con tu versión de VirtualBox
   - Abre VirtualBox → Archivo → Herramientas → Extensiones → Instala el archivo descargado

2. **Habilitar Soporte de USB en la VM**
   - Apaga tu máquina virtual si está funcionando
   - Selecciona la VM en VirtualBox → Configuración → Puertos → USB
   - Activa el `Controlador USB 2.0 (EHCI)` o `Controlador USB 3.0 (xHCI)`

3. **Conectar Dispositivo USB a la VM**
   - Inicia la VM y conecta el dispositivo USB a tu máquina física
   - En el menú de la VM: Dispositivos → USB → Selecciona tu dispositivo conectado
   - La VM tomará control del dispositivo USB

#### Paso 2: Acceder al Editor de Políticas de Grupo
- Presiona `Win + R`, escribe `gpedit.msc`, y presiona Enter
- Esto abre el Editor de Políticas de Grupo para configuración de políticas

### 🔒 Restricción de Dispositivos USB en Windows

#### Paso 3: Configurar Políticas de Restricción USB

1. **Navegar a las Políticas de Dispositivos Removibles**
   - Ve a: `Configuración del equipo > Plantillas administrativas > Sistema > Acceso de almacenamiento removible`

2. **Configurar Políticas de Denegación de Acceso USB**
   Activa las siguientes políticas para restringir el acceso USB:
   - **Discos extraíbles: denegar acceso de lectura** - Impide que los usuarios lean dispositivos USB
   - **Discos extraíbles: denegar acceso de escritura** - Impide que los usuarios escriban en dispositivos USB

   > ⚠️ **Resultado**: Esto evitará que los usuarios puedan leer o escribir en dispositivos USB conectados.

3. **Aplicar Cambios**
   - Reinicia la máquina virtual para aplicar los cambios de política

### 🧪 Validación y Prueba de la Restricción de USB

#### Paso 4: Probar las Restricciones USB

1. **Prueba la Restricción de USB**
   - Conecta un dispositivo USB a la VM
   - Intenta acceder al dispositivo desde una cuenta de usuario estándar (sin privilegios administrativos)

2. **Verificar la Restricción de Acceso**
   - Si las políticas están correctamente configuradas, los usuarios estándar no podrán acceder al dispositivo USB
   - Debería aparecer un mensaje indicando la denegación de acceso

### 👤 Creación y Prueba de un Usuario Regular

#### Paso 5: Crear Usuario Estándar para Pruebas

1. **Crear Nuevo Usuario Regular en Windows**
   - Abre **Configuración** (`Win + I`)
   - Navega a: **Cuentas > Familia y otros usuarios**

2. **Agregar Cuenta de Usuario**
   - Haz clic en **Agregar a otra persona a este equipo**
   - Selecciona **No tengo la información de inicio de sesión**
   - Luego selecciona **Agregar un usuario sin cuenta de Microsoft**
   - Crea el usuario con nombre y contraseña (será un usuario estándar, sin privilegios)

3. **Probar Restricción con Usuario Regular**
   - Inicia sesión con la nueva cuenta de usuario regular
   - Conecta el dispositivo USB para verificar que el acceso sea denegado debido a las restricciones aplicadas

### 🔧 Habilitación de Excepciones para Usuarios Específicos

#### Configuración Avanzada (Ejercicio de Investigación)

Asumimos que a este punto eres un alumno confiado en ti mismo, por lo que te pedimos que investigues cómo habilitar excepciones para usuarios específicos. La idea es que:

1. Inicies sesión con una cuenta con privilegios de administrador
2. Abras el **Editor de Políticas de Grupo**
3. Investigues cómo habilitar excepciones en las políticas de dispositivos USB para ciertos usuarios o grupos de usuarios

Por último, deberías verificar que las excepciones han sido aplicadas, realizando pruebas con diferentes usuarios.



<!-- hide -->

## Colaboradores

Gracias a estas personas maravillosas ([emoji key](https://github.com/kentcdodds/all-contributors#emoji-key)):

1. [Rosinni Rodriguez (rosinni)](https://github.com/rosinni) contribution: (build-tutorial) ✅, (documentation) 📖
  
2. [Alejandro Sanchez (alesanchezr)](https://github.com/alesanchezr),  contribution: (bug reports) 🐛

Este proyecto sigue la especificación [all-contributors](https://github.com/kentcdodds/all-contributors). ¡Todas las contribuciones son bienvenidas!

Este y otros ejercicios son usados para [aprender a programar](https://4geeksacademy.com/es/aprender-a-programar/aprender-a-programar-desde-cero) por parte de los alumnos de 4Geeks Academy [Coding Bootcamp](https://4geeksacademy.com/us/coding-bootcamp) realizado por [Alejandro Sánchez](https://twitter.com/alesanchezr) y muchos otros contribuyentes. Conoce más sobre nuestros [Cursos de Programación](https://4geeksacademy.com/es/curso-de-programacion-desde-cero?lang=es) para convertirte en [Full Stack Developer](https://4geeksacademy.com/es/coding-bootcamps/desarrollador-full-stack/?lang=es), o nuestro [Data Science Bootcamp](https://4geeksacademy.com/es/coding-bootcamps/curso-datascience-machine-learning).Tambien puedes adentrarte al mundo de ciberseguridad con nuestro [Bootcamp de ciberseguridad](https://4geeksacademy.com/es/coding-bootcamps/curso-ciberseguridad).

<!-- endhide -->

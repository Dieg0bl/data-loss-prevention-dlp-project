<!-- hide -->
#  Políticas de Seguridad DLP

> **📚 REPOSITORIO ARCHIVADO**: Este repositorio está archivado y es de solo lectura. [Haz un fork](../../fork) para trabajar con los ejercicios.

> By [@rosinni](https://github.com/rosinni) and [other contributors](https://github.com/breatheco-de/data-loss-prevention-dlp-project/graphs/contributors) at [4Geeks Academy](https://4geeksacademy.co/)

[![build by developers](https://img.shields.io/badge/build_by-Developers-blue)](https://4geeks.com)
[![build by developers](https://img.shields.io/twitter/follow/4geeksacademy?style=social&logo=twitter)](https://twitter.com/4geeksacademy)
[![Repository Status](https://img.shields.io/badge/status-archived-red)](https://github.com/Dieg0bl/data-loss-prevention-dlp-project)

*Estas instrucciones estan [disponibles en español](https://github.com/breatheco-de/data-loss-prevention-dlp-project/blob/main/README.es.md)*

### Antes de empezar...

> ¡Te necesitamos! Estos ejercicios se crean y mantienen en colaboración con personas como tú. Si encuentras algún error o falta de ortografía, contribuye y/o repórtalo.

<!-- endhide -->

## 🌱 ¿Cómo empezar este proyecto?
Este ejercicio se enfoca en la creación e implementación de políticas de seguridad para la **Prevención de Pérdida de Datos (DLP)** dentro de una organización, aplicando el principio del menor privilegio y asegurando que solo el personal autorizado tenga acceso a datos sensibles.

### 🔑 Objetivo General:
- **Parte 1**: Definir y establecer políticas de DLP que ayuden a proteger la información confidencial.
- **Parte 2**: Implementar medidas específicas, como la **restricción del uso de dispositivos USB**, para asegurar que las políticas de DLP se apliquen en la práctica.

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


### Configuración de una maquina para el acceso a dispositivos USB

> ⚠ Para llevar a cabo esta practica y aplicar restricciones de acceso a dispositivos USB, deberemos asegurarnos que la VM que estemos trabajando pueda acceder a los dispositivos USB conectados a tu máquina física (host). Sigue estos pasos:

1. **Instalar VirtualBox Extension Pack**. Ve al [sitio oficial de VirtualBox](https://www.virtualbox.org/wiki/Downloads) y descarga el Extension Pack que coincida con la versión instalada.
2. Abre VirtualBox, ve a **Archivo >herramientas > Extensiones** y selecciona el archivo descargado para instalarlo.
3. **Habilitar Soporte de USB en la VM**. Apaga la máquina virtual si está corriendo y selecciona la VM en VirtualBox, haz clic en **Configuración > Puertos > USB** y activa el **Controlador USB 2.0 (EHCI)** o **Controlador USB 3.0 (xHCI)**, según el puerto que uses.
4. **Conecta el dispositivo USB a la VM**. Inicia la VM y conecta el dispositivo USB a tu máquina física. En el menú de la VM, selecciona **Dispositivos > USB** y elige el dispositivo que conectaste. La VM tomará control del USB.

¡Una vez hecho con exito esto, comencemos!

### Restricción de Dispositivos USB en Windows

1. **Abrir el Editor de Políticas de Grupo (Group Policy Editor)**. Presiona `Win + R`, escribe `gpedit.msc` y presiona `Enter` para abrir el Editor de Políticas de Grupo.

2. **Navegar a las Políticas de Dispositivos Removibles**. Ve a `Configuración del equipo > Plantillas administrativas > Sistema > Acceso de almacenamiento removible`.

3. **Configurar la Política de Prohibición de Acceso a Dispositivos USB**. Activa las siguientes políticas:
     - **Discos extraíbles: denegar acceso de lectura**.
     - **Discos extraíbles: denegar acceso de escritura**.

> Esto evitará que los usuarios puedan leer o escribir en dispositivos USB conectados.

4. Reinicia la máquina virtual para aplicar los cambios.

### Validación y prueba de la restricción de USB

1. **Prueba la restricción de USB**. Conecta un dispositivo USB a la VM e intenta acceder al dispositivo desde una cuenta de usuario estándar (sin privilegios administrativos).

2. **Verificar la Restricción de Acceso**. Si las políticas están correctamente configuradas, los usuarios estándar no podrán acceder al dispositivo USB, y debería aparecer un mensaje indicando la denegación.

### Creación y prueba de un usuario regular

1. **Crear un nuevo usuario regular en Windows**. Abre **Configuración (Win + I)**, ve a **Cuentas > Familia y otros usuarios**.
2. Haz clic en **Agregar a otra persona a este equipo** y selecciona **No tengo la información de inicio de sesión** y luego **Agregar un usuario sin cuenta de Microsoft**.
3. Crea el usuario con nombre y contraseña (será un usuario estándar, sin privilegios).

4. **Prueba la restricción con el usuario regular**. Inicia sesión con el nuevo usuario regular y conecta el dispositivo USB para verificar que no tenga acceso debido a las restricciones aplicadas.

### Habilitación de excepciones para usuarios específicos.

Asumimos que ha este punto eres un alumno confiando en ti mismo por lo que te pedimos que investigues como habilitar excepciones para usuarios específicos. La idea seria que inicies sesión con una cuenta con privilegios de administrador y que abras el **editor de políticas de grupo** e investigues cómo habilitar excepciones en las políticas de dispositivos USB para ciertos usuarios o grupos de usuarios.

Por ultimo deberias deberias verificar que las excepciones han sido aplicadas, realizando pruebas con diferentes usuarios.



<!-- hide -->

## Colaboradores

Gracias a estas personas maravillosas ([emoji key](https://github.com/kentcdodds/all-contributors#emoji-key)):

1. [Rosinni Rodriguez (rosinni)](https://github.com/rosinni) contribution: (build-tutorial) ✅, (documentation) 📖
  
2. [Alejandro Sanchez (alesanchezr)](https://github.com/alesanchezr),  contribution: (bug reports) 🐛

Este proyecto sigue la especificación [all-contributors](https://github.com/kentcdodds/all-contributors). ¡Todas las contribuciones son bienvenidas!

Este y otros ejercicios son usados para [aprender a programar](https://4geeksacademy.com/es/aprender-a-programar/aprender-a-programar-desde-cero) por parte de los alumnos de 4Geeks Academy [Coding Bootcamp](https://4geeksacademy.com/us/coding-bootcamp) realizado por [Alejandro Sánchez](https://twitter.com/alesanchezr) y muchos otros contribuyentes. Conoce más sobre nuestros [Cursos de Programación](https://4geeksacademy.com/es/curso-de-programacion-desde-cero?lang=es) para convertirte en [Full Stack Developer](https://4geeksacademy.com/es/coding-bootcamps/desarrollador-full-stack/?lang=es), o nuestro [Data Science Bootcamp](https://4geeksacademy.com/es/coding-bootcamps/curso-datascience-machine-learning).Tambien puedes adentrarte al mundo de ciberseguridad con nuestro [Bootcamp de ciberseguridad](https://4geeksacademy.com/es/coding-bootcamps/curso-ciberseguridad).

<!-- endhide -->

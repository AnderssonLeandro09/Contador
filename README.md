# Contador

Propósito del sistema
---------------------
Aplicación web tipo contador que permite incrementar y mostrar un valor. Se utiliza aquí como ejemplo práctico para desplegar en Azure App Service.

Autor
-----
Andersson Leandro Ambuludi Gomez (AnderssonLeandro09)

Despliegue manual en Azure (Portal)

Descripción
-----------
Este repositorio contiene una aplicación ligera que se despliega manualmente en Azure App Service usando el Portal de Azure. Este documento describe paso a paso cómo preparé y desplegué la aplicación aprovechando la suscripción Azure for Students.

Audiencia
--------
Este README está dirigido a desarrolladores que necesiten desplegar manualmente una aplicación web (Node.js u otra pila soportada) en Azure App Service desde el Portal.

Requisitos previos
------------------
- Cuenta de Azure activa (en este caso: Azure for Students). Asegúrate de tener los créditos y tu suscripción habilitada.
- Código de la aplicación preparado para producción (p. ej. `npm install` y `npm start` localmente). Verificando su funcionamiento.


Resumen de pasos
----------------
1. Crear o verificar la suscripción Azure (Azure Students).
2. Crear un Grupo de Recursos.
3. Crear un App Service Plan (elige SKU según necesidades).
4. Crear un App Service (Web App) y configurar runtime (Node, versión, etc.).
5. Desplegar el código (manual o conectando con repositorio).
6. Configurar Application Settings si es necesario (variables de entorno, PORT, etc.).
7. Verificar logs y corregir errores.

Guía detallada — despliegue manual desde el Portal
-------------------------------------------------

1) Activar y verificar Azure for Students
- Accede a https://portal.azure.com y confirma que tu suscripción aparece como **Azure for Students** y que tienes crédito disponible.

2) Crear un Grupo de Recursos
- En el Portal busca "Grupos de recursos" > + Crear.
- Elige la suscripción, nombre (ej. `contador-manual`) y región (p. ej. `Central US`, `Canada Central` u otra cercana). En este caso a mi me funcionó **Canada Central**.

3) Crear App Service Plan
- Busca "App Service plans" > + Crear.
- Selecciona la suscripción y el grupo de recursos creado.


4) Crear App Service (Web App)
- Busca "App Services" > + Crear.
- Rellena la información básica:
	- Suscripción: tu suscripción Azure Students.
	- Grupo de recursos: `grupocontador`.
	- Nombre: nombre único global (ej. `contadorweb`).
	- Publicar: Código.
	- Pila de ejecución (Runtime stack): **Node 22 LTS**.. o el que uses.
	- Sistema operativo: Linux o Windows según tu preferencia.
	- App Service plan: el plan que creaste.
- Crear el recurso y esperar a la finalización.

5) Despliegue manual 
- En este repositorio enlacé el App Service con mi cuenta de GitHub y con el repositorio. Tras completar la configuración y el primer despliegue, el Portal de Azure generó la URL pública (dominio) de la aplicación y quedó accesible desde esa dirección. 
- En resumen: vinculé el repositorio → Azure realizó el despliegue → obtuve el dominio público.

7) Verificar el despliegue y logs
- Accede al dominio que te arroja al finalizar **.azurewebsites.net**. Por ejemplo:
    https://contadorweb-cqbthud2cxgahuaj.canadacentral-01.azurewebsites.net/



Limitaciones y notas sobre Azure for Students
--------------------------------------------
- Azure for Students otorga créditos y acceso gratuito a recursos seleccionados; algunas regiones pueden no estar disponibles para este tipo de suscripción.
- Verifica límites de consumo y el estado de crédito antes de crear recursos que incrementen costos.

Resolución de problemas comunes
-------------------------------
- La mayoría de errores se presenta gracias a las regiones, solo toca asegurarse de las regiones disponibles.


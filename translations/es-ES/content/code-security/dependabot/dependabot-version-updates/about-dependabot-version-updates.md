---
title: Acerca de las actualizaciones a la versión del Dependabot
intro: 'Puede utilizar el {% data variables.product.prodname_dependabot %} para mantener los paquetes que utilizas actualizados a su versión más reciente.'
redirect_from:
  - /github/administering-a-repository/about-dependabot
  - /github/administering-a-repository/about-github-dependabot
  - /github/administering-a-repository/about-github-dependabot-version-updates
  - /github/administering-a-repository/about-dependabot-version-updates
  - /code-security/supply-chain-security/about-dependabot-version-updates
  - /code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/upgrading-from-dependabotcom-to-github-native-dependabot
  - /code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/about-dependabot-version-updates
versions:
  fpt: '*'
  ghec: '*'
  ghes: '> 3.2'
type: overview
topics:
  - Dependabot
  - Version updates
  - Repositories
  - Dependencies
  - Pull requests
shortTitle: Actualizaciones de versión del dependabot
---

{% data reusables.dependabot.beta-security-and-version-updates %}
{% data reusables.dependabot.enterprise-enable-dependabot %}

## Acerca de {% data variables.product.prodname_dependabot_version_updates %}

El {% data variables.product.prodname_dependabot %} hace el esfuerzo de mantener tus dependencias. Puedes utilizarlo para garantizar que tu repositorio se mantenga automáticamente con los últimos lanzamientos de los paquetes y aplicaciones de los que depende.

You enable {% data variables.product.prodname_dependabot_version_updates %} by checking a _dependabot.yml_ configuration file into your repository. Este archivo de configuración especifica la ubicación del manifiesto o de otros archivos de definición de paquetes almacenados en tu repositorio. El {% data variables.product.prodname_dependabot %} utiliza esta información para revisar los paquetes y las aplicaciones desactualizadas. El {% data variables.product.prodname_dependabot %} determina si hay una versión nueva de una dependencia al buscar el versionamiento semántico ([semver](https://semver.org/)) de la dependencia para decidir si debería actualizarla a esa versión. Para ciertos administradores de paquetes, {% data variables.product.prodname_dependabot_version_updates %} también es compatible con su delegación a proveedores. Las dependencias delegadas (o almacenadas en caché) son aquellas que se registran en un directorio específico en un repositorio en vez de que se referencien en un manifiesto. Las dependencias delegadas a proveedores están disponibles desde el momento de su creación, incluso si los servidores de paquetes no se encuentran disponibles. Las {% data variables.product.prodname_dependabot_version_updates %} pueden configurarse para verificar las dependencias delegadas a proveedores para las nuevas versiones y también pueden actualizarse de ser necesario.

Cuando el {% data variables.product.prodname_dependabot %} identifica una dependencia desactualizada, levanta una solicitud de extracción para actualizar el manifiesto a su última versión de la dependencia. Lara las dependencias delegadas a proveedores, el {% data variables.product.prodname_dependabot %} levanta una solicitud de cambios para reemplazar la dependencia desactualizada directamente con la versión nueva. Verificas que tu prueba pase, revisas el registro de cambios y notas de lanzamiento que se incluyan en el resumen de la solicitud de extracción y, posteriormente, lo fusionas. Para obtener más información, consulta la sección "[Configurar las actualizaciones de versión del {% data variables.product.prodname_dependabot %}](/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/enabling-and-disabling-dependabot-version-updates)".

Si habilitas las _actualizaciones de seguridad_, el {% data variables.product.prodname_dependabot %} también levantará solicitudes de cambios para actualizar las dependencias vulnerables. Para obtener más información, consulta la sección "[Acerca de las {% data variables.product.prodname_dependabot_security_updates %}](/github/managing-security-vulnerabilities/about-dependabot-security-updates)".

{% data reusables.dependabot.pull-request-security-vs-version-updates %}

{% data reusables.dependabot.dependabot-tos %}

## Frecuencia de las solicitudes de extracción del {% data variables.product.prodname_dependabot %}

Tú eres quien especifica qué tan a menudo se revisa cada ecosistema para encontrar nuevas versiones en el archivo de configuración: diario, semanalmente, o mensualmente.

{% data reusables.dependabot.initial-updates %}

Si habilitaste las actualizaciones de seguridad, algunas veces verás solicitudes de extracción adicionales para actualizaciones de seguridad. Esto se activa con una alerta del {% data variables.product.prodname_dependabot %} para una dependencia en tu rama predeterminada. El {% data variables.product.prodname_dependabot %} levanta automáticamente una solicitud de extracción para actualizar la dependencia vulnerable.

## Repositorios y ecosistemas compatibles
<!-- If you make changes to this feature, check whether any of the changes affect languages listed in /get-started/learning-about-github/github-language-support. If so, please update the language support article accordingly. -->

Puedes configurar las actualizaciones de versión para los repositorios que contengan un manifiesto de dependencias o un archivo fijado para alguno de los administradores de paquetes compatibles. Para algunos administradores de paquetes, también puedes configurar la delegación a proveedores para las dependencias. Para obtener más información, consulta la sección "[Opciones de configuración para el archivo dependabot.yml](/code-security/supply-chain-security/keeping-your-dependencies-updated-automatically/configuration-options-for-dependency-updates#vendor)".
{% note %}

{% data reusables.dependabot.private-dependencies-note %}

El {% data variables.product.prodname_dependabot %} no es compatible con dependencias privadas de {% data variables.product.prodname_dotcom %} para todos los administradores de paquetes. Consulta los detalles en la tabla a continuación.

{% endnote %}

{% data reusables.dependabot.supported-package-managers %}

Si tu repositorio ya utiliza una integración para la administración de dependencias, necesitarás inhabilitarlo antes de habilitar el {% data variables.product.prodname_dependabot %}. {% ifversion fpt or ghec %}Para obtener más información, consulta la sección "[Acerca de las integraciones](/github/customizing-your-github-workflow/about-integrations)".{% endif %}

## Acerca de las notificaciones para las actualizaciones de versión del {% data variables.product.prodname_dependabot %}

Puedes filtrar tus notificaciones en {% data variables.product.company_short %} para mostrar notificaciones para las solicitudes de cambios que creó el {% data variables.product.prodname_dependabot %}. Para obtener más información, consulta la sección "[Administrar notificaciones desde tu bandeja de entrada](/github/managing-subscriptions-and-notifications-on-github/managing-notifications-from-your-inbox)".

READ THE DOCS TEST
==================

Este es un proyecto creado como PoC para aprender a publicar en ReadTheDocs desde github teniendo en cuenta que:

* reStructuredText vs Markdown
* Se automatizará la publicación de documentación.
* Se van a necesitar versionado de producto.
* Se personaliza la documentación.

Este proyecto servirá como guía para otros proyectos.

reStructuredText vs Markdown
----------------------------

Tanto Markdown como reStructuredText son lenguajes de marcado soportados por ReadTheDocs.

Según ReadTheDocs "Markdown no admite muchas de las características de Sphinx, como el marcado en línea y las directivas. Sin embargo, funciona para contenido básico en prosa. reStructuredText es el formato preferido para la documentación técnica, lea esta publicación de blog para motivarse."

`reStructuredText <https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html>`_ es un lenguaje enriquecido para la generación de documentación técnica.

Por otro lado, `MarkDown <https://daringfireball.net/projects/markdown/syntax>`_ mucho más extendido y accesible para iniciar la documentación.

Tal y como indica Eli Bendersky en su artículo `reStructuredText vs. Markdown for technical documentation <https://eli.thegreenplace.net/2017/restructuredtext-vs-markdown-for-technical-documentation/>`_ reST es un lenguaje de marcado más apropiado para cualquier tipo de documentación técnica, mientras que markdown es más apropiado para documentación más ligera.

Como conclusion, sugiero la utilización de reST como base documental en futuros documentos y probar su viabilidad.

Automatización de la publicación
--------------------------------

Siguiendo las instrucciones en la `documentación de read the docs <https://docs.readthedocs.io/en/stable/webhooks.html>`_ se añade un webhook en el repositorio git para enlazar read the docs con el proyecto y automáticamente los documentos publicados en el repositorio se publicarán en read de docs.

Versionado
----------

Read the docs soporta múltiples versiones del repositorio. En la primera importación, lo haremos desde el repositorio por defecto a la versión `latest` que apunta a la rama por defecto del repositorio git.

Crearemos una versión `stable` de documentación si en el proyecto git creamos un tag `stable` que automáticamente se actualizará si hay cambios.

Normalmente, la versión `latest` apunta a la versión más reciente de la documentación subida en git. Si quieres que sea una rama diferente, se deberá establecer como `rama por defecto` en github.

Puedes crear un *tag* para cada versión de la documentación.

Estados de la versión
`````````````````````

* Active:
 + Active
  - Los documentos están visibles.
  - Se actualizará la documentación con cada actualización.

 + Inactive
  - Los documentos no están visibles.
  - No se actualizará la documentación con cada actualización.

* Hidden:
 + No oculto y activo
  - La versión se muestra en el selector de versiones.
  - La versión se muestra en los resultados de búsqueda.
 + Oculto y activo
  - La versión no se muestra en el selector de versiones.
  - La versión no se muestra en los resultados de búsqueda.

Ocultar una versión no la convierte en privada. Si alguien tiene un enlace a la misma podrá acceder.

Niveles de privacidad
`````````````````````

- Public
 * Accesible por todo el mundo.
- Private
 * Accesible para los usuarios con permisos de acceso. No se muestra en el selector de versiones y se obtendrá un 404 si alguien intenta acceder a la documentación sin permiso.

Versions con alarma
```````````````````

Desde Admin, Advanced Settings se puede seleccionar si una version es inestable mostrando un banner en todas las páginas.

Personalización
---------------

Se pueden utilizar un plugin de phinx para personalizar la documentación generada como `este <https://docs.citusdata.com/en/v5.0/_themes/README.html>`_.

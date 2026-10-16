# España Outdoor — base experimental Organic Maps

Este repositorio está reservado para evaluar y adaptar el código de [Organic Maps](https://github.com/organicmaps/organicmaps) como posible base cartográfica y de navegación para España Outdoor.

## Estado actual

Este repositorio no contiene todavía el código fuente de Organic Maps. El repositorio upstream es la fuente de verdad y debe importarse conservando su historial Git y sus submódulos.

Upstream: https://github.com/organicmaps/organicmaps  
Rama upstream: `master`  
Commit upstream verificado al preparar este documento: `3852be29683388cbfab3c8b0beec7ac79fc76e78`

## Procedimiento de importación recomendado

La importación completa debe realizarse desde un equipo con Git, acceso a GitHub y espacio suficiente. El repositorio upstream es muy grande y usa submódulos; no es apropiado intentar copiarlo archivo a archivo mediante la API de contenidos de GitHub.

```bash
git clone --recurse-submodules https://github.com/organicmaps/organicmaps.git
cd organicmaps
git remote rename origin upstream
git remote add origin https://github.com/Baltas80/EspanaOutdoor-OrganicMaps.git
git push -u origin master
git push origin --tags
```

Antes de ejecutar el `push`, comprobar que el repositorio destino sigue vacío y que el clon local contiene el historial y los submódulos esperados. Este procedimiento conserva el historial de Organic Maps; no debe usarse `git push --mirror`, porque podría borrar o sobrescribir referencias del destino.

## Reglas de trabajo

- Mantener este repositorio experimental separado de `Baltas80/Espana-Outdoors`.
- No integrar cambios en el proyecto principal hasta completar auditoría de licencias, compilación y pruebas en dispositivos.
- Registrar cambios propios en ramas separadas, por ejemplo `feat/espana-outdoor-integration`.
- No eliminar avisos de copyright, archivos de licencia ni atribuciones.
- El código fuente, los datos binarios de mapas y las dependencias pueden tener condiciones diferentes. Revisar `LICENSE`, `NOTICE`, `DATA_LICENSE.txt` y `.reuse/dep5` de upstream antes de distribuir una aplicación derivada.
- Si se reutilizan datos binarios, código o interfaz de Organic Maps, su README solicita una mención visible y legible de “Organic Maps Project” con enlace a https://organicmaps.app.
- Para una solución white-label o el uso de sus servidores, consultar previamente con `legal@organicmaps.app`.

## Objetivo técnico

Evaluar si Organic Maps puede aportar mapas offline, búsqueda cartográfica, navegación, rutas de senderismo y gestión GPX a España Outdoor. La compatibilidad con la arquitectura Flutter/Go existente, la identidad visual del producto, el ciclo de actualización de mapas, las obligaciones de licencias y la viabilidad de compilación deben verificarse antes de tomar una decisión de integración.

# Documentación Oficial - Gestor de Perfiles de Chrome

## Índice
1. [Descripción General](#descripción-general)
2. [Requisitos del Sistema](#requisitos-del-sistema)
3. [Estructura del Proyecto](#estructura-del-proyecto)
4. [Funcionalidades Principales](#funcionalidades-principales)
5. [Guía de Uso](#guía-de-uso)
6. [Manejo de Errores](#manejo-de-errores)
7. [Consideraciones de Seguridad](#consideraciones-de-seguridad)
8. [Limitaciones Conocidas](#limitaciones-conocidas)

## Descripción General

El Gestor de Perfiles de Chrome es una aplicación Node.js que permite gestionar múltiples instancias de Chrome con diferentes perfiles de usuario. Está diseñado para facilitar el manejo de perfiles de Chrome, permitiendo su selección, asignación de puertos y creación de instancias de manera controlada.

## Requisitos del Sistema

- Node.js (versión 14 o superior)
- Google Chrome instalado en el sistema
- Sistema operativo Windows
- Mínimo 4GB de RAM (recomendado 8GB o más)
- Espacio en disco suficiente para almacenar los perfiles de Chrome

## Estructura del Proyecto

```
.
├── profileManager.js      # Clase principal que gestiona los perfiles
├── package.json          # Dependencias y configuración del proyecto
└── Respaldos/           # Directorio de respaldos y documentación
    └── Documentacion.md  # Este archivo de documentación
```

## Funcionalidades Principales

### 1. Gestión de Perfiles
- Listado de perfiles disponibles
- Selección individual de perfiles
- Selección por rango de perfiles
- Selección de todos los perfiles disponibles

### 2. Asignación de Puertos
- Asignación individual de puertos
- Asignación por rango de puertos
- Asignación automática de puertos
- Verificación de puertos en uso

### 3. Gestión de Instancias
- Creación de instancias de Chrome
- Activación de instancias inactivas
- Cierre de instancias
- Visualización del estado de las instancias

### 4. Información Detallada
- Visualización de detalles de perfiles
- Información de instancias activas
- Estado del sistema
- Logs detallados de operaciones

## Guía de Uso

### Menú Principal
El sistema presenta un menú principal con las siguientes opciones:

1. **Listar Perfiles Disponibles**
   - Muestra todos los perfiles de Chrome disponibles en el sistema

2. **Seleccionar Perfiles**
   - Permite seleccionar perfiles individualmente
   - Permite seleccionar un rango de perfiles
   - Permite seleccionar todos los perfiles disponibles

3. **Mostrar Perfiles Seleccionados**
   - Muestra información detallada de los perfiles seleccionados
   - Incluye estado de las instancias y puertos asignados

4. **Asignar Puertos**
   - Permite asignar puertos a los perfiles seleccionados
   - Ofrece diferentes métodos de asignación

5. **Crear Instancias**
   - Crea instancias de Chrome para los perfiles seleccionados
   - Asigna los puertos configurados

6. **Activar Instancia**
   - Activa todas las instancias inactivas automáticamente
   - Muestra resumen de la operación

7. **Mostrar Estado Detallado**
   - Muestra información detallada del estado del sistema
   - Incluye información de IP, User Agent y configuración

8. **Mostrar Estructura Datos**
   - Muestra la estructura interna de los datos

9. **Cerrar Todas las Instancias**
   - Cierra todas las instancias activas de manera segura

10. **Salir**
    - Cierra todas las instancias y termina el programa

### Flujo de Trabajo Recomendado

1. Listar perfiles disponibles
2. Seleccionar los perfiles deseados
3. Asignar puertos a los perfiles seleccionados
4. Crear instancias o activar instancias inactivas
5. Verificar el estado de las instancias
6. Cerrar instancias cuando ya no sean necesarias

## Manejo de Errores

El sistema incluye manejo de errores para las siguientes situaciones:

- Perfiles no encontrados
- Puertos ya en uso
- Errores al crear instancias
- Errores al cerrar instancias
- Problemas de permisos
- Errores de conexión

Cada error es registrado con información detallada para facilitar la solución de problemas.

## Consideraciones de Seguridad

1. **Puertos**
   - Los puertos se asignan en el rango 9222-9999
   - Se verifica que los puertos no estén en uso
   - Se evita la asignación duplicada de puertos

2. **Perfiles**
   - Cada perfil mantiene su directorio de usuario separado
   - No se comparte información entre perfiles
   - Se mantiene la integridad de los datos de usuario

3. **Instancias**
   - Las instancias se ejecutan en modo headless por defecto
   - Se implementan medidas de seguridad de Chrome
   - Se manejan los recursos de manera eficiente

## Limitaciones Conocidas

1. **Rendimiento**
   - El número máximo de instancias depende de los recursos del sistema
   - Se recomienda no exceder las 10 instancias simultáneas

2. **Sistema Operativo**
   - Actualmente optimizado para Windows
   - Puede requerir ajustes para otros sistemas operativos

3. **Recursos**
   - Cada instancia consume memoria y CPU
   - Se recomienda monitorear el uso de recursos

4. **Puertos**
   - Limitado por la disponibilidad de puertos en el sistema
   - Puede requerir ajustes en sistemas con muchos servicios

---

*Última actualización: [Fecha actual]*
*Versión del documento: 1.0*

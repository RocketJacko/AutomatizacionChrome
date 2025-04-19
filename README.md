Voy a detallar cada función de la clase `ProfileManager` con su funcionamiento:

1. `constructor()`
   - Inicializa las propiedades de la clase:
     - `availableInstances`: Array para almacenar instancias disponibles
     - `perfilesChrome`: Array para almacenar perfiles de Chrome
     - `instanciasActivas`: Array para instancias activas
     - `defaultChromePath`: Ruta por defecto de los perfiles de Chrome
     - `perfilesExistentes`: Array para perfiles existentes
     - `basePort`: Puerto base para las instancias (9222)

2. `async listProfiles(chromePath = this.defaultChromePath)`
   - Lista los perfiles disponibles en Chrome
   - Verifica si existe la ruta especificada
   - Filtra y almacena los perfiles existentes
   - Retorna un array con los números de los perfiles encontrados

3. `async obtenerInformacionPerfil(browser, profileName)`
   - Obtiene información detallada de un perfil específico
   - Recopila:
     - IP del perfil
     - Información del sistema
     - Información de la ventana
     - Timestamp de la última actualización

4. `async createInstance(profileName, port, chromePath, headless = true)`
   - Crea una nueva instancia de Chrome
   - Configura el navegador con parámetros específicos
   - Obtiene información detallada de la instancia
   - Almacena la instancia en `availableInstances`
   - Retorna el objeto de la instancia creada

5. `getAvailableInstances()`
   - Retorna el array de instancias disponibles
   - Simple getter para acceder a `availableInstances`

6. `getPerfilesChrome()`
   - Retorna el array de perfiles de Chrome
   - Simple getter para acceder a `perfilesChrome`

7. `async closeInstance(profileName)`
   - Cierra una instancia específica
   - Busca la instancia por nombre
   - Cierra el navegador
   - Elimina la instancia de los arrays correspondientes

8. `seleccionarUnPerfil(perfiles)`
   - Permite al usuario seleccionar un perfil individual
   - Muestra lista de perfiles disponibles
   - Valida la selección del usuario
   - Almacena el perfil seleccionado en `perfilesChrome`

9. `seleccionarRangoPerfiles(perfiles)`
   - Permite seleccionar un rango de perfiles
   - Solicita inicio y fin del rango
   - Valida el rango seleccionado
   - Almacena los perfiles del rango en `perfilesChrome`

10. `async crearInstanciasParaPerfiles()`
    - Crea instancias para todos los perfiles seleccionados
    - Asigna puertos secuencialmente
    - Crea instancias en modo headless
    - Maneja errores durante la creación

11. `async mostrarPerfilesSeleccionados()`
    - Muestra los perfiles que han sido seleccionados
    - Lista nombre y puerto de cada perfil
    - Muestra mensaje si no hay perfiles seleccionados

12. `async mostrarEstadoDetallado()`
    - Muestra estado detallado de todas las instancias
    - Crea una tabla con información de:
      - Perfil
      - Puerto
      - Modo
      - IP
      - Plataforma
      - Idioma
      - Resolución
      - Zona horaria
      - Tamaños de ventana
      - Última actualización

13. `async mostrarInstanciasActivas()`
    - Muestra las instancias actualmente activas
    - Proporciona opción para ver detalles de una instancia específica
    - Muestra información básica y detallada según selección

14. `async abrirInstanciasParalelo()`
    - Abre múltiples instancias simultáneamente
    - Permite especificar cuántas instancias abrir
    - Crea instancias en modo headless
    - Muestra estado de cada instancia creada

15. `async cerrarTodasLasInstancias()`
    - Cierra todas las instancias activas
    - Recorre el array de instancias activas
    - Cierra cada navegador
    - Limpia los arrays de instancias

Cada función está diseñada para trabajar en conjunto, permitiendo una gestión completa de perfiles e instancias de Chrome, desde la selección hasta la creación y monitoreo de instancias.


mostrarMenuPrincipal(): Este método muestra el menú principal con dos opciones:
Seleccionar Perfiles
Salir
mostrarSubmenuPerfiles(): Este método muestra el submenú de perfiles con las siguientes opciones:
Perfiles
Validar Perfiles Seleccionados
Crear Instancias
Ver Detalles Instancias
Abrir Instancias
Cerrar Instancias
Volver al Menú Principal
Características del menú implementado:
Navegación intuitiva:
Menú principal con opción de salida
Submenú con todas las funcionalidades solicitadas
Opción para volver al menú principal
Manejo de errores:
Validación de opciones inválidas
Mensajes de error claros
Pausa para leer mensajes antes de continuar
Integración con funciones existentes:
Utiliza todos los métodos existentes de la clase
Mantiene la funcionalidad original
Agrega una capa de interfaz de usuario
Características adicionales:
Limpieza de pantalla entre menús
Pausas para leer mensajes
Cierre seguro al salir
Para usar el nuevo menú, simplemente necesitas llamar al método mostrarMenuPrincipal() de una instancia de ProfileManager. Por ejemplo:
Apply to profileManag...
El menú es interactivo y guiará al usuario a través de todas las funcionalidades disponibles de manera organizada y clara.


## Listado de Variables y Funciones Principales del Código

### Variables de clase (`this`)
- `this.availableInstances` - Almacena las instancias disponibles  
- `this.perfilesChrome` - Almacena los perfiles de Chrome seleccionados  
- `this.instanciasActivas` - Almacena las instancias activas  
- `this.defaultChromePath` - Ruta por defecto de los perfiles de Chrome  
- `this.perfilesExistentes` - Lista de perfiles existentes  
- `this.basePort` - Puerto base para las instancias  

### Funciones principales
- `mostrarSubmenuPerfiles()` - Muestra el submenú de perfiles  
- `listProfiles()` - Lista los perfiles disponibles  
- `obtenerInformacionPerfil()` - Obtiene información de un perfil  
- `createInstance()` - Crea una instancia de Chrome  
- `getAvailableInstances()` - Obtiene las instancias disponibles  
- `getPerfilesChrome()` - Obtiene los perfiles de Chrome  
- `closeInstance()` - Cierra una instancia  
- `seleccionarUnPerfil()` - Selecciona un perfil individual  
- `seleccionarRangoPerfiles()` - Selecciona un rango de perfiles  
- `crearInstanciasParaPerfiles()` - Crea instancias para los perfiles seleccionados  
- `mostrarPerfilesSeleccionados()` - Muestra los perfiles seleccionados  
- `mostrarEstadoDetallado()` - Muestra el estado detallado  
- `mostrarInstanciasActivas()` - Muestra las instancias activas  
- `abrirInstanciasParalelo()` - Abre instancias en paralelo  
- `cerrarTodasLasInstancias()` - Cierra todas las instancias  

### Variables locales comunes
- `perfiles` - Lista de perfiles disponibles  
- `profileName` - Nombre del perfil  
- `perfilInfo` - Información del perfil  
- `instance` - Instancia de Chrome  
- `port` - Puerto de la instancia  
- `page` - Página de Chrome  
- `userAgent` - User agent del navegador  
- `platform` - Plataforma del sistema  
- `language` - Idioma del sistema  
- `vendor` - Proveedor del navegador  
- `screenInfo` - Información de la pantalla  
- `windowInfo` - Información de la ventana  
- `ipData` - Datos de IP  




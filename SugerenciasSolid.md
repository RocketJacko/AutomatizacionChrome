# Aplicación de Principios SOLID al Proyecto `ProfileManager` con JSDoc

Este documento describe cómo aplicar los principios **SOLID** al proyecto de gestión de perfiles de Chrome, utilizando documentación con **JSDoc** y estructuras basadas en interfaces.

---

## 🧱 Principio de Responsabilidad Única (SRP)

**Objetivo:** Cada clase debe tener una única responsabilidad.

**Reestructuración sugerida:**

- **`ProfileSelector`**: Encargada únicamente de la selección de perfiles.
- **`PortManager`**: Responsable de gestionar la asignación de puertos.
- **`InstanceManager`**: Encargada de crear, cerrar y manejar instancias de Chrome.
- **`MenuManager`**: Gestiona la lógica de menús e interacción con el usuario.

---

## 🔐 Principio Abierto/Cerrado (OCP)

**Objetivo:** Las clases deben estar **abiertas a extensión** pero **cerradas a modificación**.

**Sugerencias:**

- Usar **interfaces base** para cada tipo de funcionalidad.
- Crear **clases abstractas** con comportamientos comunes reutilizables.
- Permitir la extensión de funcionalidad creando nuevas clases sin alterar las existentes.

---

## 🔁 Principio de Sustitución de Liskov (LSP)

**Objetivo:** Las subclases deben poder sustituir a sus clases padre sin alterar el comportamiento del sistema.

**Sugerencias:**

- Definir **contratos claros** mediante interfaces.
- Documentar con JSDoc para establecer expectativas.
- Asegurar que las implementaciones respeten las firmas y comportamientos.

---

## 🔍 Principio de Segregación de Interfaces (ISP)

**Objetivo:** Ninguna clase debe depender de métodos que no utiliza.

**Sugerencias:**

- Crear **interfaces específicas** y separadas por funcionalidad.
- Evitar interfaces genéricas con métodos innecesarios.
- Implementar solo lo que se necesita por contexto.

---

## 🔌 Principio de Inversión de Dependencias (DIP)

**Objetivo:** Las clases deben depender de **abstracciones**, no de implementaciones concretas.

**Sugerencias:**

- Usar **inyección de dependencias** para pasar servicios.
- Separar instanciación y lógica de negocio.
- Mantener las dependencias desacopladas.

---

## 📘 Ejemplo de Interfaces con JSDoc

```ts
/**
 * @interface ProfileSelectorInterface
 * @description Define el contrato para la selección de perfiles
 */
interface ProfileSelectorInterface {
  /**
   * @method selectProfile
   * @param {string} profileName - Nombre del perfil a seleccionar
   * @returns {Promise<Profile>}
   */
  selectProfile(profileName: string): Promise<Profile>;

  /**
   * @method selectProfileRange
   * @param {number} start - Inicio del rango
   * @param {number} end - Fin del rango
   * @returns {Promise<Profile[]>}
   */
  selectProfileRange(start: number, end: number): Promise<Profile[]>;
}



/**
 * @interface PortManagerInterface
 * @description Define el contrato para la gestión de puertos
 */
interface PortManagerInterface {
  /**
   * @method assignPort
   * @param {Profile} profile - Perfil al que asignar el puerto
   * @param {number} port - Puerto a asignar
   * @returns {Promise<boolean>}
   */
  assignPort(profile: Profile, port: number): Promise<boolean>;

  /**
   * @method isPortAvailable
   * @param {number} port - Puerto a verificar
   * @returns {Promise<boolean>}
   */
  isPortAvailable(port: number): Promise<boolean>;
}


/**
 * @interface InstanceManagerInterface
 * @description Define el contrato para la gestión de instancias
 */
interface InstanceManagerInterface {
  /**
   * @method createInstance
   * @param {Profile} profile - Perfil para crear la instancia
   * @returns {Promise<Instance>}
   */
  createInstance(profile: Profile): Promise<Instance>;

  /**
   * @method closeInstance
   * @param {Instance} instance - Instancia a cerrar
   * @returns {Promise<void>}
   */
  closeInstance(instance: Instance): Promise<void>;
}
````

## ✅ Beneficios de Esta Estructura

### 🛠 Mejor Mantenibilidad
- Cada clase tiene una única responsabilidad.
- Las dependencias están bien definidas.
- El código es más fácil de entender y extender.

### 🧪 Mayor Testabilidad
- Puedes crear **mocks** fácilmente para pruebas.
- Cada componente puede testearse de forma aislada.
- Las interfaces permiten crear múltiples implementaciones.

### 🔄 Mayor Flexibilidad
- Cambiar una implementación no afecta al resto del sistema.
- Se puede extender sin modificar código existente.
- Mejora la integración con configuraciones diferentes.

### 📚 Mejor Documentación
- Las interfaces son **contratos explícitos y auto-documentados**.
- JSDoc facilita la generación de documentación automática.
- Claridad sobre lo que cada componente espera y entrega.

### 🗂 Mejor Organización
- Arquitectura **modular y escalable**.
- Fácil colaboración en equipo.
- Fomenta el uso de buenas prácticas.

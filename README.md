# ParcialT1_CVDS: Juan Pabo Camargo Teheran

MonitorStock: Documentación del Proyecto
### Introducción
MonitorStock es un proyecto que se enfoca en la gestión de productos y su inventario. A continuación, se explican las decisiones de diseño y patrones utilizados en el proyecto.

### Decisiones de Diseño
Patrón de Microservicios
Se optó por una arquitectura basada en microservicios para lograr una mayor modularidad y escalabilidad. Cada funcionalidad (por ejemplo, gestión de productos, usuarios, pedidos, etc.) se implementa como un microservicio independiente. Esto permite desplegar, escalar y mantener cada componente de manera aislada.

#### Clase ServiceResponse
La clase ServiceResponse se utiliza para encapsular las respuestas de los servicios. Proporciona una estructura uniforme para manejar errores, mensajes y datos devueltos. Por ejemplo, al obtener la lista de productos, el controlador puede devolver un ServiceResponse con la lista de productos o un mensaje de error si algo falla.

#### Inyección de Dependencias en la Clase Config
La inyección de dependencias se realiza en la clase Config. Aquí se configuran los beans necesarios para los servicios, como repositorios, servicios externos o componentes personalizado.

#### Patrón Modelo-Controlador (MVC)
El patrón Modelo-Controlador se utiliza para separar las responsabilidades en capas. En nuestro caso:

#### Modelo: Representa las entidades del dominio (por ejemplo, Product).
#### Controlador: Maneja las solicitudes HTTP y coordina la lógica de negocio.
Vista: Aunque no se menciona en la estructura del proyecto, en una aplicación web, la vista sería la interfaz de usuario.

#### Patrón Singleton para la Clase de Base de Datos
Para evitar múltiples conexiones a la base de datos, se implementó un patrón Singleton en la clase que actúa como base de datos. Esto garantiza que solo exista una instancia de la conexión a la base de datos en toda la aplicación.
# Anexo: Los 4 pilares fundamentales en D.O.O.
* Abstraccion
* Herencia
* Polimorfismo
* Encapsulamiento

## Abstraccion:
La abstracción es el proceso de ocultar los detalles complejos y mostrar solo la información esencial, permitiendo enfocarse únicamente en los aspectos más relevantes para el sistema en desarrollo. En programación orientada a objetos, se utiliza para simplificar la interacción con un sistema al exponer únicamente los elementos necesarios y ocultar la implementación interna.

Cuando estamos diseñando un sistema, abstraemos lo más importante: es decir, identificamos las características clave que el sistema necesita para funcionar correctamente y nos deshacemos de los detalles que no son relevantes para el problema en cuestión. Esto permite que el sistema sea más fácil de entender, de modificar y de extender, ya que los componentes internos pueden cambiar sin afectar a los usuarios o a las partes del sistema que interactúan con ellos.

**En resumen la abstracción es como identificar lo más importante de un problema o sistema, y concentrarse en esos aspectos clave para desarrollar una solución que sea más manejable y comprensible.**

### Ejemplo con diagrama de clases.

![Diagrama UML](https://github.com/Lavianach/Mis-Entregas/raw/main/DiagramaClasesdrawio.png)

[Diagrama UML en Draw.io](https://drive.google.com/file/d/16V6FEHywA3oYAP07dxAyf7sJyU3MsT8P/view?usp=sharing)

Como dijimos antes abstraccion hace referencia a obtener solamente lo que realmente necesitamos dejando de lado lo menos importante. Se puede ver en los atributos que menciono en cada clase mostrando asi al usuario solamente lo que el necesita para poder realizar su obejetivo, evitando asi molestias y tambien poder hacer el sistema mas flexible y adaptable.

### Ejemplo codigo
Clase Bibliotecario que hereda de Persona
public class Usuario extends Persona {

    Implementación de métodos heredados de Persona

    public void iniciarSesion() {
        System.out.println("Iniciando sesión");
    }
    public void generarCodigoID(int id) {
        System.out.println("Generando código de ID " + id);
    }
    public void generarPrestamo() {
        System.out.println("Generando préstamo ");
    }
    public void obtenerInformacion() {
        System.out.println("Obteniendo información ");
    }

    
    public void realizarDevolucion() {
        System.out.println("Realizando devolución del libro");
    }
    public void realizarPago() {
        System.out.println("Realizando pago ");
    }

## Herencia 
La herencia es uno de los pilares fundamentales del diseño orientado a objetos (OOP) y es un mecanismo que permite que una clase herede propiedades y comportamientos (métodos) de otra. En otras palabras, una clase hija puede heredar atributos y métodos de una clase padre, lo que promueve la reutilización del código y la creación de estructuras jerárquicas.Simplicando herencia permite que una clase derive (o herede) de otra. La clase hija o derivada tiene todos los atributos y métodos de la clase padre o base, y puede agregar, modificar o extender esos métodos según sea necesario.
Ejemplo similar a abstraccion.

![Diagrama UML](https://github.com/Lavianach/Mis-Entregas/raw/main/DiagramaClasesdrawio.png)
[Diagrama UML en Draw.io](https://drive.google.com/file/d/16V6FEHywA3oYAP07dxAyf7sJyU3MsT8P/view?usp=sharing)

**Descripcion** En este ejemplo si podemos visualizar la herencia con la clase abastracta _Persona_ , donde sus 2 clases hijas Usuario y Bibliotecario heredan atributos y metodos de ella evitando asi repetir codigo. Siendo hijas las 2 se puede notar que comparten el padre pero de todas formas una actua diferente de la otra. 
Me parecio mas claro este ejemplo de herencia que en el ejemplo anterior de abastraccion,  al pilar abastraccion lo veo mas como sacar lo importate y mostrar eso, lo que el usuario o el que este visualizando  le sea adatable sin tener extensiones de cosas que por ahi no necesita saber o hacerlas.
### Ejemplo codigo

 //Clase abstracta Persona
 
public abstract class Persona {
    private String nombreUsuario;
    private String direccion;
    private String correo;
    private String contraseña;

    // Constructor
    public Persona(String nombreUsuario, String direccion, String correo, String contraseña) {
        this.nombreUsuario = nombreUsuario;
        this.direccion = direccion;
        this.correo = correo;
        this.contraseña = contraseña;
   

    public void obtenerInformacion() {
        System.out.println("Nombre de usuario: " + nombreUsuario);
        System.out.println("Dirección: " + direccion);
        System.out.println("Correo: " + correo);
    }
    // Clase Usuario que hereda de Persona
    
     public class Usuario extends Persona {
     public Usuario(String nombreUsuario, String direccion, String correo, String contraseña) {
        super(nombreUsuario, direccion, correo, contraseña);
    }

    @Override
    public void obtenerInformacion() {
        System.out.println("Usuario: " + nombreUsuario);
        System.out.println("Correo electrónico: " + correo);
    }
}
## Polimorfismo
En programación orientada a objetos el polimorfismo permite que una misma acción o método tenga diferentes comportamientos dependiendo del objeto que la invoque. Por ejemplo podemos tener un metodo "mensaje" que se vea diferente dependiendo quien la invoque, puede ser un mensaje de gmail, una notificacion y otra a red social, seria un mismo metodo pero accionaria de forma diferente depende quien lo tome como dije antes.

![Diagrama UML](https://github.com/Lavianach/Mis-Entregas/raw/main/DiagramaClasesdrawio.png)

[Diagrama UML en Draw.io](https://drive.google.com/file/d/16V6FEHywA3oYAP07dxAyf7sJyU3MsT8P/view?usp=sharing)

Vamos a implementar el método iniciarSesion como un ejemplo de polimorfismo tanto Usuario como el Bibliotecario heredan de la clase abstracta Persona y cada uno tendrá su propia lógica para el inicio de sesión.
En la clase abstracta Persona, definimos el método abstracto iniciarSesion, que será sobrescrito en las subclases (Usuario y Bibliotecario).
Desde el sistema principal, usamos el polimorfismo para manejar ambas clases (Usuario y Bibliotecario) de forma genérica

EJMPLO CON CODIGO JAVA.

// Clase abstracta Persona
abstract class Persona {
    protected String nombreUsuario;
    protected String contraseña;

    // Constructor
    public Persona(String nombreUsuario, String contraseña) {
        this.nombreUsuario = nombreUsuario;
        this.contraseña = contraseña;
    }

    // Método abstracto para iniciar sesión
    public abstract void iniciarSesion();
}

// Clase Usuario
class Usuario extends Persona {

    public Usuario(String nombreUsuario, String contraseña) {
        super(nombreUsuario, contraseña);
    }

    @Override
    public void iniciarSesion() {
        System.out.println("Inicio de sesión exitoso para el Usuario: " + nombreUsuario);
        // Lógica adicional específica para un Usuario
        System.out.println("Accediendo al sistema ");
    }
}

// Clase Bibliotecario
class Bibliotecario extends Persona {

    public Bibliotecario(String nombreUsuario, String contraseña) {
        super(nombreUsuario, contraseña);
    }

    @Override
    public void iniciarSesion() {
        System.out.println("Inicio de sesión exitoso para el Bibliotecario: " + nombreUsuario);
        // Lógica adicional específica para un Bibliotecario
        System.out.println("Accediendo al sistema de gestión de libros...");
    }
}
// Clase principal para probar
public class SistemaBiblioteca {
    public static void main(String[] args) {
       
        // Creamos un Usuario
        Persona usuario = new Usuario("Pedito", "123456");

        // Creamos un Bibliotecario
        Persona bibliotecario = new Bibliotecario("OscarGomez", "oscarsito123");

        // Polimorfismo en acción: ambos inician sesión de manera diferente
        usuario.iniciarSesion(); 
        // Salida:
        // Inicio de sesión exitoso para el Usuario: usuario123
        // Accediendo al sistema de préstamos...

        bibliotecario.iniciarSesion();
        // Salida:
        // Inicio de sesión exitoso para el Bibliotecario: admin123
        // Accediendo al sistema de gestión de libros...
    }
}
## Encapsulamiento:

El encapsulamiento es uno de los principios fundamentales de la programación orientada a objetos (OOP), y se refiere al concepto de ocultar los detalles internos de una clase y exponer solo lo necesario a través de interfaces públicas. Esto se logra utilizando modificadores de acceso (como private, protected y public) para controlar cómo los datos de una clase pueden ser accedidos y modificados desde otras clases.

El encapsulamiento implica la agrupación de datos (atributos) y métodos (funciones) en una sola unidad, que es la clase. Este principio ayuda a controlar el acceso a los datos y asegura que el estado de los objetos esté siempre consistente.
Importancia del Encapsulamiento:
Protección de datos: Al hacer que los atributos sean privados, evitamos que otros objetos o clases modifiquen el estado de un objeto directamente. Solo los métodos de la clase pueden manipular sus datos internos, lo que garantiza que el objeto se mantenga en un estado válido y consistente.
Facilita la mantenimiento y la escalabilidad: Si los detalles internos de una clase cambian, los métodos de la clase pueden adaptarse sin que las clases que usen esta clase tengan que ser modificadas. Esto permite realizar cambios en el diseño sin afectar a otros componentes del sistema.
Control de acceso: A través de los métodos getter y setter, podemos validar o realizar tareas adicionales antes de permitir la modificación o acceso a los atributos. Por ejemplo, podemos asegurarnos de que solo se asignen valores válidos a los atributos.
Mejora la legibilidad y reutilización del código: Al ocultar los detalles internos y proporcionar una interfaz clara y controlada, el código es más fácil de leer y comprender, lo que facilita su reutilización en otros contextos o aplicaciones.
![Diagrama UML](https://github.com/Lavianach/Mis-Entregas/raw/main/DiagramaClasesdrawio.png)
[Diagrama UML en Draw.io](https://drive.google.com/file/d/16V6FEHywA3oYAP07dxAyf7sJyU3MsT8P/view?usp=sharing)
Justamente lo que hice en el sistema como fue poner los atributos en private que es uno de los principios del encapsulamiento.En el sistema se aplico el principio de encapsulamiento al declarar los atributos como private, lo que garantiza que los datos internos de las clases no sean accesibles directamente desde fuera. De esta manera, solo se puede acceder a la información a través de los métodos getters y setters, proporcionando control sobre cómo se leen y modifican los valores. Este enfoque asegura que los usuarios solo puedan interactuar con los datos que necesitan, mejorando la seguridad y la integridad del sistema."

EJEMPLO CON CODIGO JAVA.
public abstract class Persona {
    // Atributos privados
    private String nombreUsuario;
    private String direccion;
    private String correo;
    private String contraseña;

    // Constructor
    public Persona(String nombreUsuario, String direccion, String correo, String contraseña) {
        this.nombreUsuario = nombreUsuario;
        this.direccion = direccion;
        this.correo = correo;
        this.contraseña = contraseña;
    }

    // Métodos getter y setter
    public String getNombreUsuario() {
        return nombreUsuario;
    }

    public void setNombreUsuario(String nombreUsuario) {
        this.nombreUsuario = nombreUsuario;
    }

    public String getDireccion() {
        return direccion;
    }

    public void setDireccion(String direccion) {
        this.direccion = direccion;
    }

    public String getCorreo() {
        return correo;
    }

    public void setCorreo(String correo) {
        this.correo = correo;
    }

    public String getContraseña() {
        return contraseña;
    }

    public void setContraseña(String contraseña) {
        this.contraseña = contraseña;
    }

    // Método abstracto que debe ser implementado en las clases hijas
    public abstract void iniciarSesion();
}
public class Usuario extends Persona {

    // Constructor
    public Usuario(String nombreUsuario, String direccion, String correo, String contraseña) {
        super(nombreUsuario, direccion, correo, contraseña);
    }

    // Implementación del método abstracto
    @Override
    public void iniciarSesion() {
        // Aquí podrías poner la lógica para validar que el nombre de usuario y contraseña son correctos
        System.out.println("Inicio de sesión para el usuario: " + getNombreUsuario());
    }

    // Método adicional
    public void obtenerInformacion() {
        System.out.println("Nombre de usuario: " + getNombreUsuario());
        System.out.println("Dirección: " + getDireccion());
        System.out.println("Correo: " + getCorreo());
    }
}























    

















    









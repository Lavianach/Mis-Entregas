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





    

















    









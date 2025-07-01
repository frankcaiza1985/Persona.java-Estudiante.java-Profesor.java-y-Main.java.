# Persona.java-Estudiante.java-Profesor.java-y-Main.java.
// Persona.java
public class Persona {
    // Atributos privados → encapsulación
    private String nombre;
    private int edad;

    // Constructor
    public Persona(String nombre, int edad) {
        this.nombre = nombre;
        this.edad = edad;
    }

    // Getters y Setters
    public String getNombre() {
        return nombre;
    }
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    public int getEdad() {
        return edad;
    }
    public void setEdad(int edad) {
        this.edad = edad;
    }

    // Método que puede ser sobrescrito (polimorfismo)
    public String presentarse() {
        return "Hola, soy " + nombre + ", tengo " + edad + " años.";
    }

    // Ejemplo de sobrecarga: saludo sin argumentos
    public String saludar() {
        return "¡Hola!";
    }

    // Ejemplo de sobrecarga: saludo personalizado
    public String saludar(String otroNombre) {
        return "¡Hola, " + otroNombre + "! Soy " + nombre + ".";
    }

    @Override
    public String toString() {
        return "Persona[nombre=" + nombre + ", edad=" + edad + "]";
    }
}
// Estudiante.java
public class Estudiante extends Persona {
    private String carrera;
    private double promedio;

    public Estudiante(String nombre, int edad, String carrera, double promedio) {
        super(nombre, edad);  // llama al constructor de la clase base
        this.carrera = carrera;
        this.promedio = promedio;
    }

    public String getCarrera() {
        return carrera;
    }
    public void setCarrera(String carrera) {
        this.carrera = carrera;
    }
    public double getPromedio() {
        return promedio;
    }
    public void setPromedio(double promedio) {
        this.promedio = promedio;
    }

    // Sobrescritura del método presentarse()
    @Override
    public String presentarse() {
        return super.presentarse() + " Estudio " + carrera + " y tengo un promedio de " + promedio + ".";
    }

    @Override
    public String toString() {
        return "Estudiante[" + super.toString() + ", carrera=" + carrera + ", promedio=" + promedio + "]";
    }
}
// Profesor.java
public class Profesor extends Persona {
    private String departamento;
    private int antiguedad;

    public Profesor(String nombre, int edad, String departamento, int antiguedad) {
        super(nombre, edad);
        this.departamento = departamento;
        this.antiguedad = antiguedad;
    }

    public String getDepartamento() {
        return departamento;
    }
    public void setDepartamento(String departamento) {
        this.departamento = departamento;
    }
    public int getAntiguedad() {
        return antiguedad;
    }
    public void setAntiguedad(int antiguedad) {
        this.antiguedad = antiguedad;
    }

    // Sobrescritura del método presentarse()
    @Override
    public String presentarse() {
        return super.presentarse() + " Trabajo en el área de " + departamento + " con " + antiguedad + " años de antigüedad.";
    }

    @Override
    public String toString() {
        return "Profesor[" + super.toString() + ", departamento=" + departamento + ", antiguedad=" + antiguedad + "]";
    }
}
// Main.java
public class Main {
    public static void main(String[] args) {
        // Creación de instancias
        Persona p = new Persona("María", 35);
        Estudiante e = new Estudiante("Juan", 20, "Ingeniería", 8.5);
        Profesor prof = new Profesor("Carlos", 50, "Matemáticas", 15);

        // Uso de métodos y demostración de polimorfismo
        System.out.println(p.presentarse());
        System.out.println(p.saludar());
        System.out.println(p.saludar("Ana"));
        System.out.println(p);

        System.out.println();

        System.out.println(e.presentarse());
        System.out.println(e.saludar());
        System.out.println(e.saludar("Lucía"));
        System.out.println(e);

        System.out.println();

        System.out.println(prof.presentarse());
        System.out.println(prof.saludar());
        System.out.println(prof.saludar("Equipo"));
        System.out.println(prof);
    }
}

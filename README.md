
    package ganancias;


    public abstract class Vendedor {
    protected double sueldobase; //Variable que almacenará el sueldo base del empleado
    protected double tVentas; // Variable que almacenara las ventas totales que vendio el empleado
    protected double comisiones; // Variable que almacenará las comisiones equivalentes al 10% de las ventas
    protected double sueldoTotal; // Variable que almacenará el suelo total del Empleado o Vendedor


    //Método Constructor
    public Vendedor(double sueldoBase){
        this.sueldobase = sueldoBase;
    }

    // Método Abstracto que se encargará de calcular las ventas Totales
    public abstract void calcularVentasTotales();

    // Método encargado de Calcular y devolver las comisiones
    public void getComisiones() {
        this.comisiones = this.tVentas * .10;
    }

    // Método encargado de Calcular el Salario Total del empleado
    public void getSueldoTotal() {
        this.sueldoTotal = this.sueldobase + this.comisiones;
        System.out.println("Mi salario total es de: $" + sueldoTotal);
    }
    
    package ganancias;
    //Aplicación de la Herencia, esta clase hereda los metodos y atributos de las clase Padre(Vendedor)
    public class TrabajadorBimestral extends Vendedor{

    //Atributos de la clase Hija
    private double venta1; // Variable que almacena la venta #1
    private double venta2; // Variable que almacena la venta #2
    private double venta3; // Variable que almacena la venta #3
    private double venta4; // Variable que almacena la venta #4
    private double venta5; // Variable que almacena la venta #5
    private double venta6; // Variable que almacena la venta #6

    //Método Constructor de la Clase Hija
    public TrabajadorBimestral(double sueldoBase, double venta1, double venta2, double venta3, double venta4, double venta5, double venta6) {
        super(sueldoBase); // Llamado al Método Constructor de la clase Padre(Vendedor)
        this.venta1 = venta1;
        this.venta2 = venta2;
        this.venta3 = venta3;
        this.venta4 = venta4;
        this.venta5 = venta5;
        this.venta6 = venta6;
    }

    //Redifinición del método abstracto de la Clase Padre(Vendedor) en la clase Hija
    @Override
    public void calcularVentasTotales() {
        this.tVentas = venta1 + venta2 + venta3 + venta4 + venta5 + venta6;
    }
}

    package ganancias;

    public class ventas {

    public static void main(String args[]){

        Trabajador Prueba1 = new Trabajador(3450, 1700, 2000, 5430); // Declaración del objeto Trabjador que lleva el nombre de Prueba1
        TrabajadorBimestral Prueba2 = new TrabajadorBimestral(4500, 1200, 8000, 3000, 1243, 5000, 2050); // Declaración del objeto TrabjadorBimestral que lleva el nombre de Prueba2

        Prueba1.calcularVentasTotales(); // Llamar al metodo para calcular el total de ventas que realizo el trabajador
        Prueba1.getComisiones(); // Llamar al método para calcular las comisiones de ventas
        Prueba1.getSueldoTotal(); // Llamar al método para mostrar el sueldo total del trabajador

        Prueba2.calcularVentasTotales(); // Llamar al metodo para calcular el total de ventas que realizo el trabajador
        Prueba2.getComisiones(); // Llamar al método para calcular las comisiones de ventas
        Prueba2.getSueldoTotal(); // Llamar al método para mostrar el sueldo total del trabajador
    }


}

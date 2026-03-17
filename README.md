import java.util.Scanner;
import javax.swing.JOptionPane;

public class CalculadoraConPoppas {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        // ===============================
        // DATOS DEL LOGIN
        // ===============================
        String user = "cami", pass = "1234", user1 = "", pass1 = "";
        int exit = 0;

        // ===============================
        // LOGIN DEL USUARIO
        // ===============================
        do {
            user1 = JOptionPane.showInputDialog(
                    
                    null, "ingrese su usuario",
                    "Usuario", JOptionPane.WARNING_MESSAGE
                    
                    

            );

            pass1 = JOptionPane.showInputDialog(
                    null,
                    "Ingrese su Contraseña:",
                    "CONTRASEÑA",
                    JOptionPane.INFORMATION_MESSAGE
            );

            if (user.equals(user1) && pass.equals(pass1)) {

                JOptionPane.showMessageDialog(
                        null,
                        "Inicio de Sesión correcto",
                        "INICIO DE SESIÓN",
                        JOptionPane.INFORMATION_MESSAGE
                );

                exit = 1;

            } else {

                JOptionPane.showMessageDialog(
                        null,
                        "Usuario o contraseña incorrectos",
                        "ERROR",
                        JOptionPane.ERROR_MESSAGE
                );
            }

        } while (exit == 0);

        // ===============================
        // MENÚ DE LA CALCULADORA
        // ===============================
        int opcion;

        do {

            double num1, num2, total;

            System.out.println("""
            Seleccione la operación:
            1. Suma
            2. Resta
            3. Multiplicación
            4. División
            5. Potencia
            6. Raíz
            7. Seno
            8. Coseno
            9. Tangente
            10. Salir
            """);

            opcion = scanner.nextInt();

            switch (opcion) {

                case 1:
                    System.out.print("Ingrese el primer número: ");
                    num1 = scanner.nextDouble();
                    System.out.print("Ingrese el segundo número: ");
                    num2 = scanner.nextDouble();
                    total = num1 + num2;
                    System.out.println("Resultado: " + total);
                    break;

                case 2:
                    System.out.print("Ingrese el primer número: ");
                    num1 = scanner.nextDouble();
                    System.out.print("Ingrese el segundo número: ");
                    num2 = scanner.nextDouble();
                    total = num1 - num2;
                    System.out.println("Resultado: " + total);
                    break;

                case 3:
                    System.out.print("Ingrese el primer número: ");
                    num1 = scanner.nextDouble();
                    System.out.print("Ingrese el segundo número: ");
                    num2 = scanner.nextDouble();
                    total = num1 * num2;
                    System.out.println("Resultado: " + total);
                    break;

                case 4:
                    System.out.print("Ingrese el primer número: ");
                    num1 = scanner.nextDouble();
                    System.out.print("Ingrese el segundo número: ");
                    num2 = scanner.nextDouble();

                    if (num2 != 0) {
                        total = num1 / num2;
                        System.out.println("Resultado: " + total);
                    } else {
                        System.out.println("No se puede dividir entre cero");
                    }
                    break;

                case 5:
                    System.out.print("Base: ");
                    num1 = scanner.nextDouble();
                    System.out.print("Exponente: ");
                    num2 = scanner.nextDouble();
                    System.out.println("Resultado: " + Math.pow(num1, num2));
                    break;

                case 6:
                    System.out.print("Ingrese el número: ");
                    num1 = scanner.nextDouble();
                    System.out.print("Ingrese el índice de la raíz: ");
                    num2 = scanner.nextDouble();

                    if (num2 != 0) {
                        total = Math.pow(num1, 1.0 / num2);
                        System.out.println("Resultado: " + total);
                    } else {
                        System.out.println("El índice de la raíz no puede ser cero");
                    }
                    break;

                case 7:
                    System.out.print("Ángulo en grados: ");
                    num1 = scanner.nextDouble();
                    System.out.println("Seno: " + Math.sin(Math.toRadians(num1)));
                    break;

                case 8:
                    System.out.print("Ángulo en grados: ");
                    num1 = scanner.nextDouble();
                    System.out.println("Coseno: " + Math.cos(Math.toRadians(num1)));
                    break;

                case 9:
                    System.out.print("Ángulo en grados: ");
                    num1 = scanner.nextDouble();
                    System.out.println("Tangente: " + Math.tan(Math.toRadians(num1)));
                    break;

                case 10:
                    System.out.println("Saliendo del programa...");
                    break;

                default:
                    System.out.println("Opción inválida");
            }

        } while (opcion != 10);

        scanner.close();
    }
}

# -atividade-reajuste-salarial.
Código da atividade de reajuste salarial em Java.
public class ReajusteSalarial {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Entrada do salário
        System.out.print("Digite o salário do colaborador: R$ ");
        double salario = scanner.nextDouble();

        // Variáveis para cálculo
        double percentual = 0;
        double aumento = 0;
        double salarioNovo = 0;
        double aumentoReal = 0;
        double inflacao = 3.8;

        // Determinar percentual de aumento
        if (salario <= 280) {
            percentual = 20;
        } else if (salario > 280 && salario <= 700) {
            percentual = 15;
        } else if (salario > 700 && salario <= 1500) {
            percentual = 10;
        } else {
            percentual = 5;
        }

        // Calcular o aumento
        aumento = salario * (percentual / 100);
        salarioNovo = salario + aumento;

        // Calcular aumento real descontando a inflação (apenas se > 1500)
        if (salario > 1500) {
            aumentoReal = aumento - (salario * (inflacao / 100));
        } else {
            aumentoReal = aumento;
        }

        // Exibir os resultados
        System.out.println("Salário antes do reajuste: R$ " + salario);
        System.out.println("Percentual de aumento aplicado: " + percentual + "%");
        System.out.println("Valor do aumento: R$ " + aumento);
        System.out.println("Novo salário, após o aumento: R$ " + salarioNovo);
        System.out.println("Valor do aumento real (descontada a inflação): R$ " + aumentoReal);

        scanner.close();
    }
}

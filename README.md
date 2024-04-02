//CÓDIGO FEITO PARA AULA DE LINGRAGEM DE PROGRAMAÇAÕ, COM A BIBLIOTECA RANDOM E A SCANNER. O PROJETO É BASEADO EM UMA LOTOFACIL, QUE SORTEIA NÚMEROS, LETRAS, SE O NÚMERO É IMPAR OU PAR  // DEPENDENDO DA OPÇÃO QUE O USUÁRIO ESCOLHER.
//JDK21.0.2
import java.util.Random;
import java.util.Scanner;

    public class LotoFacil {

        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);

            int opcao;
            do {
                exibirMenu();
                opcao = scanner.nextInt();
                switch (opcao) {
                    case 1:
                        apostarDe0a100(scanner);
                        break;
                    case 2:
                        apostarDeAToZ(scanner);
                        break;
                    case 3:
                        apostarParOuImpar(scanner);
                        break;
                    case 0:
                        System.out.println("Saindo do programa...");
                        break;
                    default:
                        System.out.println("Opção inválida. Por favor, escolha uma opção válida.");
                        break;
                }
            } while (opcao != 0);

            scanner.close();
        }

        public static void exibirMenu() {
            System.out.println("**************************");
            System.out.println("Menu LOTOFÁCIL:");
            System.out.println("1) Apostar de 0 a 100");
            System.out.println("2) Apostar de A à Z");
            System.out.println("3) Apostar em par ou ímpar");
            System.out.println("0) Sair");
            System.out.println("**************************");
            System.out.print("Escolha uma opção: ");
        }

        public static void apostarDe0a100(Scanner scanner) {
            Random random = new Random();
            int numeroSorteado = random.nextInt(24);

            System.out.print("Digite um número de 0 a 100: ");
            int aposta = scanner.nextInt();

            if (aposta < 0 || aposta > 100) {
                System.out.println("Aposta inválida.");
                return;
            }

            if (aposta == numeroSorteado) {
                System.out.println("Parabéns! Você ganhou R$ 1.000,00 reais.");
            } else {
                System.out.println("Que pena! O número sorteado foi: " + numeroSorteado + ".");
            }
        }

        public static void apostarDeAToZ(Scanner scanner) {
            char letraPremiada ='B';

            System.out.print("Digite uma letra de A à Z: ");
            char aposta = scanner.next().toUpperCase().charAt(0);

            if (!Character.isLetter(aposta)) {
                System.out.println("Aposta inválida.");
                return;
            }

            if (aposta == letraPremiada) {
                System.out.println("Parabéns! Você ganhou R$ 500,00 reais.");
            } else {
                System.out.println("Que pena! A letra sorteada foi: " + letraPremiada + ".");
            }
        }

        public static void apostarParOuImpar(Scanner scanner) {
            int numeroSorteado = scanner.nextInt();

            System.out.println("O número sorteado foi: " + numeroSorteado);

            if (numeroSorteado % 2 == 0) {
                System.out.println("Parabéns! Você ganhou R$ 100,00 reais.");
            } else {
                System.out.println("Que pena! O número sorteado foi ímpar.");
            }
        }
    }




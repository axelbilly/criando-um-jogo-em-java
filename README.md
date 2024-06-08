# criando-um-jogo-em-java
criando um joguinho
package Metodos;
import java.util.Random;
import java.util.Scanner;

public abstract class GeenGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random verificar = new Random();
        int casaespecial = verificar.nextInt(5) +1;
        String[]o cores = {"Amarelo", "Vermelho", "Azul", "Verde"};
        int qtdpartida;
        String[] valores = {""};
        int opcao = 0;
        int escolhapergunta = 0;
        int selecaocr;
        int partida = 0;
        int qtdJogadores = 0;
        String textovitoria = "";
        int totalCasasTabuleiro = 36;

        // Tela inicial
        while (opcao != 3) {
            ClearScrenn();
            System.out.println(

    "+----------------------------------------+\t\t+----------------------------------------+\t\t+----------------------------------------+\n" +
    "|                                        |\t\t|                                        |\t\t|                                        |\n" +
    "|                1. JOGAR                |\t\t|              2. SCORE                  |\t\t|              3.  SAIR                  |\n" +
    "|                                        |\t\t|                                        |\t\t|                                        |\n" +
    "+----------------------------------------+\t\t+----------------------------------------+\t\t+----------------------------------------+\n" +
    "\n" +
    "Pressione '1' para jogar, '2' para ver o score ou '3' para sair\n"
);

            opcao = scanner.nextInt();
            scanner.nextLine();

            ClearScrenn();

            while (opcao < 1 || opcao > 3) {
                System.out.print("\nInforme uma opção válida: ");
                opcao = scanner.nextInt();
                scanner.nextLine();
            }

            if (opcao == 1) {
                System.out.println("+-----------------------------+\n" +
                "|                             |\n" +
                "|    Seleção de personagens   |\n" +
                "|                             |\n" +
                "+-----------------------------+\n"
+
                                        "\r\n" + //
                                        "+-------------------+\t\t+-------------------+\t\t+-------------------+\n" + //
                                        "|                   |\t\t|                   |\t\t|                   |\n" + //
                                        "|   2 Jogadores     |\t\t|   3 Jogadores     |\t\t|   4 Jogadores     |\n" + //
                                        "|                   |\t\t|                   |\t\t|                   |\n" + //
                                        "+-------------------+\t\t+-------------------+\t\t+-------------------+\n" + //
                                        "");
                System.out.print("\nEscolha a quantidade de jogadores: ");
                qtdJogadores = scanner.nextInt();
                scanner.nextLine();
                
                while (qtdJogadores < 2 || qtdJogadores > 4) {
                    System.out.println("\nInforme uma quantidade válida");
                    qtdJogadores = scanner.nextInt();
                    scanner.nextLine();
                }

                Jogador[] jogadores = new Jogador[qtdJogadores];

                ClearScrenn();

                for (int i = 0; i < qtdJogadores; i++) {
                    jogadores[i] = new Jogador();
                    jogadores[i].setId(i + 1);
                    System.out.println("+-----------------------------+\n" +
                    "|                             |\n" +
                    "| Escolha o nome do jogador " + jogadores[i].getId()+ ":"+"|\n" +
                    "|                             |\n" +
                    "+-----------------------------+\n");
                    jogadores[i].setNome(scanner.nextLine());
                }

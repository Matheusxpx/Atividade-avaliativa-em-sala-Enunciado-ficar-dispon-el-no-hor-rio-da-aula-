# Atividade-avaliativa-em-sala-Enunciado-ficar-dispon-el-no-hor-rio-da-aula-
atividade

        // 6 fileiras e 8 assentos
        int[][] sala = new int[6][8];

        int opcao;

        do {
            System.out.println("\n--- MENU ---");
            System.out.println("1. Reservar assento");
            System.out.println("2. Cancelar reserva");
            System.out.println("3. Exibir mapa da sala");
            System.out.println("4. Exibir quantidade de assentos livres e ocupados");
            System.out.println("5. Encerrar");
            System.out.print("Escolha: ");
            opcao = sc.nextInt();

            switch (opcao) {

                case 1: // Reservar
                    System.out.print("Fileira (1-6): ");
                    int f = sc.nextInt() - 1;

                    System.out.print("Assento (1-8): ");
                    int a = sc.nextInt() - 1;

                    if (f >= 0 && f < 6 && a >= 0 && a < 8) {
                        if (sala[f][a] == 0) {
                            sala[f][a] = 1;
                            System.out.println("Assento reservado a reserva deve ser cancelada!");
                        } else {
                            System.out.println("Assento ja esta ocupado!");
                        }
                    } else {
                        System.out.println("Posição inválida!");
                    }
                    break;

                case 2: // Cancelar
                    System.out.print("Fileira (1-6): ");
                    f = sc.nextInt() - 1;

                    System.out.print("Assento (1-8): ");
                    a = sc.nextInt() - 1;

                    if (f >= 0 && f < 6 && a >= 0 && a < 8) {
                        if (sala[f][a] == 1) {
                            sala[f][a] = 0;
                            System.out.println("Reserva deve ser cancelada!");
                        } else {
                            System.out.println("Assento ja esta livre!");
                        }
                    } else {
                        System.out.println("Posição inválida!");
                    }
                    break;

                case 3: // Exibir mapa
                    System.out.println("\nMAPA DA SALA:");
                    for (int i = 0; i < 6; i++) {
                        System.out.print("Fileira " + (i + 1) + ": ");
                        for (int j = 0; j < 8; j++) {
                            System.out.print(sala[i][j] + " ");
                        }
                        System.out.println();
                    }
                    break;

                case 4: // Contagem
                    int livres = 0, ocupados = 0;

                    for (int i = 0; i < 6; i++) {
                        for (int j = 0; j < 8; j++) {
                            if (sala[i][j] == 0) {
                                livres++;
                            } else {
                                ocupados++;
                            }
                        }
                    }

                    int total = 6 * 8;
                    double percentual = (ocupados * 100.0) / total;

                    System.out.println("\nAssentos livres: " + livres);
                    System.out.println("Assentos ocupados: " + ocupados);
                    System.out.printf("Percentual de ocupacao da sala: %.2f%%\n", percentual);
                    break;

                case 5:
                    System.out.println("Encerrando...");
                    break;

                default:
                    System.out.println("Opção inválida!");
            }

        } while (opcao != 5);

        sc.close();
    }
}

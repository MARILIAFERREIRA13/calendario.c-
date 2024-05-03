# calendario.c-
Trabalho AV1 - Agenda de compromissos

#include <stdio.h>

// Função para inserir agendamento em um único dia
void inserirAgendamento(int *agenda, int dia) {
  // Verifica se há conflitos de agendamento
  if (agenda[dia - 1] >= 5) {
    printf(
        "Não é possível agendar para o dia %d. Limite de pacientes excedido.\n",
        dia);
    return;
  }

  // Insere o agendamento
  agenda[dia - 1]++;
  printf("Agendamento realizado com sucesso!\n");
}

// Função para mostrar o calendário
void mostrarCalendario(int primeiroDiaJaneiro) {
  int diasNoMes[] = {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};
  char *nomesMeses[] = {"Janeiro",  "Fevereiro", "Março",    "Abril",
                        "Maio",     "Junho",     "Julho",    "Agosto",
                        "Setembro", "Outubro",   "Novembro", "Dezembro"};

  printf("*** CALENDÁRIO ***\n");
  for (int mes = 0; mes < 12; mes++) {
    printf("\n%s\n", nomesMeses[mes]);
    printf("Dom Seg Ter Qua Qui Sex Sab\n");
    for (int i = 0; i < primeiroDiaJaneiro; i++) {
      printf("    ");
    }
    for (int dia = 1; dia <= diasNoMes[mes]; dia++) {
      printf("%3d ", dia);
      if ((dia + primeiroDiaJaneiro) % 7 == 0 || dia == diasNoMes[mes]) {
        printf("\n");
      }
    }
    primeiroDiaJaneiro = (primeiroDiaJaneiro + diasNoMes[mes]) % 7;
  }
}

// Função para mostrar o calendário com agendamentos
void mostrarCalendarioComAgendamentos(int *agenda) {
  int diasNoMes[] = {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};
  char *nomesMeses[] = {"Janeiro",  "Fevereiro", "Março",    "Abril",
                        "Maio",     "Junho",     "Julho",    "Agosto",
                        "Setembro", "Outubro",   "Novembro", "Dezembro"};

  printf("*** CALENDÁRIO DE AGENDAMENTOS ***\n");
  for (int mes = 0; mes < 12; mes++) {
    printf("%s\n", nomesMeses[mes]);
    printf("Dom Seg Ter Qua Qui Sex Sab\n");
    for (int dia = 0; dia < diasNoMes[mes]; dia++) {
      printf("%3d ", agenda[dia]);
      if ((dia + 1) % 7 == 0) {
        printf("\n");
      }
    }
    printf("\n");
  }
}

int main() {
  int primeiroDiaJaneiro, bissexto;
  int agenda[365] = {0}; // Inicializando todos os dias sem agendamentos

  printf("Digite o dia da semana em que 1º de janeiro cai (0 para domingo, 1 "
         "para segunda, etc.): ");
  scanf("%d", &primeiroDiaJaneiro);

  printf("O ano é bissexto? (1 para sim, 0 para não): ");
  scanf("%d", &bissexto);

  int opcao;
  do {
    printf("\nMenu:\n");
    printf("1. Mostrar calendário\n");
    printf("2. Inserir agendamento\n");
    printf("3. Mostrar calendário com agendamentos\n");
    printf("4. Sair\n");
    printf("Escolha uma opção: ");
    scanf("%d", &opcao);

    switch (opcao) {
    case 1:
      mostrarCalendario(primeiroDiaJaneiro);
      break;
    case 2: {
      int dia;
      printf("Digite o dia do agendamento: ");
      scanf("%d", &dia);
      inserirAgendamento(agenda, dia);
      break;
    }
    case 3:
      mostrarCalendarioComAgendamentos(agenda);
      break;
    case 4:
      printf("Saindo do programa...\n");
      break;
    default:
      printf("Opção inválida!\n");
    }
  } while (opcao != 4);

  return 0;
}

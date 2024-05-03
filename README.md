# calendario.c-
Trabalho AV1 - Agenda de compromissos

Grupo:
1 - Henrique Dias
2 - Roberto Salomão
3 - Marilia Ferreira

Inclusão das Bibliotecas: No início do código, incluímos a biblioteca <stdio.h>, que é necessária para entrada e saída de dados.
Declaração das Funções: Definimos as funções inserirAgendamento, mostrarCalendario e mostrarCalendarioComAgendamentos. Essas funções serão utilizadas posteriormente no código para realizar tarefas específicas.
Função inserirAgendamento: Esta função é responsável por inserir um agendamento em um dia específico. Ela recebe como parâmetro o array agenda (que guarda o número de agendamentos para cada dia) e o dia em que o agendamento deve ser feito. Ela verifica se já existem 5 agendamentos para o dia escolhido. Se sim, exibe uma mensagem informando que não é possível agendar mais. Se não, incrementa o contador de agendamentos para esse dia e exibe uma mensagem de sucesso.
Função mostrarCalendario: Esta função é responsável por exibir o calendário de um ano. Ela utiliza o algoritmo para calcular os dias da semana com base no dia da semana em que 1º de janeiro cai. Ela exibe o calendário mês a mês, mostrando os dias da semana e os números dos dias.
Função mostrarCalendarioComAgendamentos: Esta função é responsável por exibir o calendário com os agendamentos. Ela mostra o número de agendamentos para cada dia do ano, mês a mês.
Função main: Esta é a função principal do programa. Ela solicita ao usuário o dia da semana em que 1º de janeiro cai e se o ano é bissexto ou não. Em seguida, entra em um loop de menu que permite ao usuário escolher entre:
Mostrar o calendário.
Inserir um agendamento para um dia específico.
Mostrar o calendário com os agendamentos.
Sair do programa.
Dependendo da escolha do usuário, a função chama a função correspondente para realizar a tarefa desejada.
Em resumo, este código implementa um sistema simples de gerenciamento de agendamentos para um fisioterapeuta, permitindo que ele veja o calendário, agende pacientes para determinados dias e visualize os agendamentos feitos.

tivemos um problema para colocar o agendamento em um dia do mes escolhido, não conseguimos resolver.

https://replit.com/@MariliaRamos/PROG-2-Trabalho-AV1-Agenda-de-compromissos#main.c

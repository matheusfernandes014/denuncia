# denuncia
denuncia roubo
#include <stdio.h>
#include <string.h>

#define CODIGO_SEGURANCA "1234" // Código de segurança pré-definido
#define MAX_TENTATIVAS 3 // Número máximo de tentativas

int main() {
    char codigo_usuario[10];
    int tentativas = 0;
    int acesso_concedido = 0;

    printf("Sistema de Alarme - Por favor, insira o código de segurança.\n");

    while (tentativas < MAX_TENTATIVAS) {
        // Solicita o código de segurança ao usuário
        printf("Código: ");
        scanf("%s", codigo_usuario);

        // Verifica se o código inserido está correto
        if (strcmp(codigo_usuario, CODIGO_SEGURANCA) == 0) {
            acesso_concedido = 1;
            break;
        } else {
            tentativas++;
            printf("Código incorreto. Tentativas restantes: %d\n", MAX_TENTATIVAS - tentativas);
        }
    }

    // Verifica se o acesso foi concedido
    if (acesso_concedido) {
        printf("Acesso concedido.\n");
    } else {
        printf("Número máximo de tentativas excedido. Alarme ativado!\n");
        // Aqui, você pode adicionar código para ativar o alarme, como uma mensagem para o administrador ou gravação em um arquivo de log.
    }

    return 0;
}




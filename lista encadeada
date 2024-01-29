#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <stdbool.h>

struct _idNode {
    int* info;
    struct _idNode* next;
};
typedef struct _idNode idNode;

idNode* tabelaSimbolos;

void insereNo(idNode* no) {
    no->next = tabelaSimbolos;
    tabelaSimbolos = no;
}

idNode* alocaNo(int* info) {
    idNode* no = malloc(sizeof(idNode));
    if (no == NULL) {
        printf("Memória esgotada.\n");
        exit(0);
    }
    no->info = info;
    no->next = NULL;
    return no;
}

void liberaNo(idNode* no) {
    printf("no liberado com sucesso!\n");
    free(no->info);
    free(no);
}
void imprimeSimbolo(int* info) {
    idNode* aux = tabelaSimbolos;
    while (aux != NULL) {
        if (info == aux->info) {
            printf("Value: %d\n", *aux->info);
            return;
        }
        aux = aux->next;
    }
    printf("Simbolo nao encontrado.\n");
}

void Testa() {
    int* valor = malloc(sizeof(int));
    *valor = 5;
    int* valor2 =malloc(sizeof(int));
    *valor2 = 7;
    idNode* no = alocaNo(valor);
    idNode* no2 = alocaNo(valor2);
    insereNo(no);
    imprimeSimbolo(valor);
    insereNo(no2);
    liberaNo(no);
    imprimeSimbolo(valor2);
    liberaNo(no2);
}

int main() {
    Testa();
    return 0;
}

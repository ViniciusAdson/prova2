Lista avaliativa 2

Questão 1

#include <stdio.h>

int main(){
    int num = 10;
    int valores[10];
    int conjunto_novo[10];
    for (int i = 0; i < num; i++) {
        scanf("%d", &valores[i]);
    }
    while (num > 1)
    {
         for (int i = 0; i < num; i++) {
            printf("%d", valores[i]);
            
            if (i < num - 1) {
                printf(" ");
             }
         }
         printf("\n");
         for (int i = 0; i < num - 1; i++)
         {
            conjunto_novo[i] = valores[i] + valores[i+1];
         }
         num--;
         for (int i = 0; i < num; i++)
         {
            valores[i] = conjunto_novo[i];
         }
         
    }
    printf("%d\n", valores[0]);
    


    return 0;
}

Questão 2
#include <stdio.h>

float calculaForcaPonderada(int forcas[]) {
    return (8 * forcas[0] + 10 * (forcas[1] + forcas[2]) + 5 * (forcas[3] + forcas[4]) + 8 * (forcas[5] + forcas[6]) + 11 * (forcas[7] + forcas[8]) + 12 * (forcas[9] + forcas[10])) / 100.0;
}

int main() {
    int forcasTimeA[11] = {0}, forcasTimeB[11] = {0};
    char nomeTimeA[31], nomeTimeB[31];
    char nomeJogador[31], posicaoJogador;
    int forcaJogador;
    
    
    scanf(" %30[^\n]", nomeTimeA);
    for (int i = 0; i < 11; i++) {
        scanf(" %30[^;]; %c; %d", nomeJogador, &posicaoJogador, &forcaJogador);

        int posicao = (posicaoJogador == 'L') ? (forcasTimeA[1] == 0) ? 1 : 2 : 
        (posicaoJogador == 'Z') ? (forcasTimeA[3] == 0) ? 3 : 4 : 
        (posicaoJogador == 'V') ? (forcasTimeA[5] == 0) ? 5 : 6 : 
        (posicaoJogador == 'M') ? (forcasTimeA[7] == 0) ? 7 : 8 : 
        (posicaoJogador == 'A') ? (forcasTimeA[9] == 0) ? 9 : 10 : 0;

        if (forcasTimeA[posicao] == 0)
            forcasTimeA[posicao] = forcaJogador;
    }

    scanf(" %30[^\n]", nomeTimeB);
    for (int i = 0; i < 11; i++) {
        scanf(" %30[^;]; %c; %d", nomeJogador, &posicaoJogador, &forcaJogador);

        int posicao = (posicaoJogador == 'L') ? (forcasTimeB[1] == 0) ? 1 : 2 : 
        (posicaoJogador == 'Z') ? (forcasTimeB[3] == 0) ? 3 : 4 : 
        (posicaoJogador == 'V') ? (forcasTimeB[5] == 0) ? 5 : 6 : 
        (posicaoJogador == 'M') ? (forcasTimeB[7] == 0) ? 7 : 8 : 
        (posicaoJogador == 'A') ? (forcasTimeB[9] == 0) ? 9 : 10 : 0;

        if (forcasTimeB[posicao] == 0)
            forcasTimeB[posicao] = forcaJogador;
    }

    float forcaTimeA = calculaForcaPonderada(forcasTimeA);
    float forcaTimeB = calculaForcaPonderada(forcasTimeB);

    printf("%s: %.2f de forca\n%s: %.2f de forca\n", nomeTimeA, forcaTimeA, nomeTimeB, forcaTimeB);

    if (forcaTimeA > forcaTimeB)
        printf("%s eh mais forte\n", nomeTimeA);
    else if (forcaTimeB > forcaTimeA)
        printf("%s eh mais forte\n", nomeTimeB);
    else
        printf("Os times têm a mesma forca\n");

    return 0;
}

QUESTÃO 3

#include <stdio.h>
#include <string.h>


int main(){
    int matrizA[4][4];
    int matrizB[4][4];
    int resultado[4][4];
    char operacao[5];
    
    for (int i = 0; i < 4; i++)
    {
      for (int j = 0; j < 4; j++)
      {
         scanf("%d",&matrizA[i][j]);
      }
    }
    for (int i = 0; i < 4; i++)
    {
      for (int j = 0; j < 4; j++)
      {
         scanf("%d",&matrizB[i][j]);
      }
    }

    scanf("%s", operacao);

    if (strcmp(operacao,"soma")==0)
    {
        for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                resultado[i][j] = matrizA[i][j] + matrizB[i][j];
            }
        }
     }
    else if (strcmp(operacao,"sub")==0)
    {
       for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                resultado[i][j] = matrizA[i][j] - matrizB[i][j];
            }
       }
    }
    else if (strcmp(operacao,"mult")==0)
    {
        for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                resultado[i][j]=0;
                
                for (int k = 0; k < 4; k++) {
                  resultado[i][j] += matrizA[i][k] * matrizB[k][j];
                 }
            }
        }
    }
    
    
    for (int i = 0; i < 4; i++)
    {
      for (int j = 0; j < 4; j++)
      {
         printf("%*d",+4,resultado[i][j]);
      }
      printf("\n");
    }
    return 0;
}Lista avaliativa 2

Questão 1

#include <stdio.h>

int main(){
    int num = 10;
    int valores[10];
    int conjunto_novo[10];
    for (int i = 0; i < num; i++) {
        scanf("%d", &valores[i]);
    }
    while (num > 1)
    {
         for (int i = 0; i < num; i++) {
            printf("%d", valores[i]);
            
            if (i < num - 1) {
                printf(" ");
             }
         }
         printf("\n");
         for (int i = 0; i < num - 1; i++)
         {
            conjunto_novo[i] = valores[i] + valores[i+1];
         }
         num--;
         for (int i = 0; i < num; i++)
         {
            valores[i] = conjunto_novo[i];
         }
         
    }
    printf("%d\n", valores[0]);
    


    return 0;
}

Questão 2
#include <stdio.h>

float calculaForcaPonderada(int forcas[]) {
    return (8 * forcas[0] + 10 * (forcas[1] + forcas[2]) + 5 * (forcas[3] + forcas[4]) + 8 * (forcas[5] + forcas[6]) + 11 * (forcas[7] + forcas[8]) + 12 * (forcas[9] + forcas[10])) / 100.0;
}

int main() {
    int forcasTimeA[11] = {0}, forcasTimeB[11] = {0};
    char nomeTimeA[31], nomeTimeB[31];
    char nomeJogador[31], posicaoJogador;
    int forcaJogador;
    
    
    scanf(" %30[^\n]", nomeTimeA);
    for (int i = 0; i < 11; i++) {
        scanf(" %30[^;]; %c; %d", nomeJogador, &posicaoJogador, &forcaJogador);

        int posicao = (posicaoJogador == 'L') ? (forcasTimeA[1] == 0) ? 1 : 2 : 
        (posicaoJogador == 'Z') ? (forcasTimeA[3] == 0) ? 3 : 4 : 
        (posicaoJogador == 'V') ? (forcasTimeA[5] == 0) ? 5 : 6 : 
        (posicaoJogador == 'M') ? (forcasTimeA[7] == 0) ? 7 : 8 : 
        (posicaoJogador == 'A') ? (forcasTimeA[9] == 0) ? 9 : 10 : 0;

        if (forcasTimeA[posicao] == 0)
            forcasTimeA[posicao] = forcaJogador;
    }

    scanf(" %30[^\n]", nomeTimeB);
    for (int i = 0; i < 11; i++) {
        scanf(" %30[^;]; %c; %d", nomeJogador, &posicaoJogador, &forcaJogador);

        int posicao = (posicaoJogador == 'L') ? (forcasTimeB[1] == 0) ? 1 : 2 : 
        (posicaoJogador == 'Z') ? (forcasTimeB[3] == 0) ? 3 : 4 : 
        (posicaoJogador == 'V') ? (forcasTimeB[5] == 0) ? 5 : 6 : 
        (posicaoJogador == 'M') ? (forcasTimeB[7] == 0) ? 7 : 8 : 
        (posicaoJogador == 'A') ? (forcasTimeB[9] == 0) ? 9 : 10 : 0;

        if (forcasTimeB[posicao] == 0)
            forcasTimeB[posicao] = forcaJogador;
    }

    float forcaTimeA = calculaForcaPonderada(forcasTimeA);
    float forcaTimeB = calculaForcaPonderada(forcasTimeB);

    printf("%s: %.2f de forca\n%s: %.2f de forca\n", nomeTimeA, forcaTimeA, nomeTimeB, forcaTimeB);

    if (forcaTimeA > forcaTimeB)
        printf("%s eh mais forte\n", nomeTimeA);
    else if (forcaTimeB > forcaTimeA)
        printf("%s eh mais forte\n", nomeTimeB);
    else
        printf("Os times têm a mesma forca\n");

    return 0;
}

QUESTÃO 3

#include <stdio.h>
#include <string.h>


int main(){
    int matrizA[4][4];
    int matrizB[4][4];
    int resultado[4][4];
    char operacao[5];
    
    for (int i = 0; i < 4; i++)
    {
      for (int j = 0; j < 4; j++)
      {
         scanf("%d",&matrizA[i][j]);
      }
    }
    for (int i = 0; i < 4; i++)
    {
      for (int j = 0; j < 4; j++)
      {
         scanf("%d",&matrizB[i][j]);
      }
    }

    scanf("%s", operacao);

    if (strcmp(operacao,"soma")==0)
    {
        for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                resultado[i][j] = matrizA[i][j] + matrizB[i][j];
            }
        }
     }
    else if (strcmp(operacao,"sub")==0)
    {
       for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                resultado[i][j] = matrizA[i][j] - matrizB[i][j];
            }
       }
    }
    else if (strcmp(operacao,"mult")==0)
    {
        for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 4; j++) {
                resultado[i][j]=0;
                
                for (int k = 0; k < 4; k++) {
                  resultado[i][j] += matrizA[i][k] * matrizB[k][j];
                 }
            }
        }
    }
    
    
    for (int i = 0; i < 4; i++)
    {
      for (int j = 0; j < 4; j++)
      {
         printf("%*d",+4,resultado[i][j]);
      }
      printf("\n");
    }
    return 0;
}

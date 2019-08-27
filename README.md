# baksetballproject
meu primeiro projeto 

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <math.h>


int main()
{
    int i = 0 , j = 0, opcao, d, k , n=10;
    char jogadores[10][100], nomeMenor[100], nomeMaior[100], tempNome[100];
    float alt[10], media = 0, maior, menor, dp = 0, total = 0, numJogadores, aux, mediana;

    printf("Camila de Paula Amaral RA: 21284723 \n");
    printf("Henrique Alves da Costa RA: 21321625 \n");
    printf("Higor Souza de Almeida RA: 21296312 \n");

    printf("\n");

    for(i = 0; i <10; i++){
        printf("Digite o Nome do  jogador: \n");
        gets(jogadores[i]);
    }

    for(j = 0; j <10; j++){
        fflush(stdin);
        printf("Digite suas alturas: \n");
        scanf("%f", &alt[j]);
      if( alt[j] <= 0){
        printf("Altura invalida, por favor digite novamente: \n");
        scanf("%f", &alt[j]);
      }
    }

   printf("\n");

    if(!( opcao == 1 || opcao == 2 || opcao == 3 || opcao == 4 || opcao == 5 || opcao == 6)){
    }
    while(opcao != 6){
    printf("====== TIME DE BASQUETE ======\n");
    printf("1- Dados dos Jogadores \n");
    printf("2- Media das Alturas \n");
    printf("3- Desvio Padrao das Alturas \n");
    printf("4- Maior e Menor Altura \n");
    printf("5- Mediana das Alturas \n");
    printf("6- Finalizar \n");
    printf("Digite uma opcao: \n");
    scanf("%i", &opcao);

    if(!( opcao == 1 || opcao == 2 || opcao == 3 || opcao == 4 || opcao == 5 || opcao == 6)){
        printf("Opcao Invalida, por favor digite novamente a opcao desejada: \n");
        scanf("%i", &opcao);
    }
    switch(opcao){
    case 1:
            printf("===== OPCAO 1 SELECIONADA ===== \n");
        for(i=0; i<10 ;i++){
            printf("nome: %s\n", jogadores[i]);
            printf("altura: %.2f\n", alt[i] );
        }
        break;
    case 2:
            printf("===== OPCAO 2 SELECIONADA ===== \n");
            media = (alt[0] + alt[1] + alt[2] + alt[3] + alt[4] + alt[5] + alt[6] + alt[7] + alt[8] + alt[9] ) / 10;
            printf("A media eh: %.2f\n", media );
        break;
    case 3:
                if(media == 0){
            printf("E necessario primeiro clicar no item 2 \n");
        }else{
        for(d = 0; d < numJogadores; d++){
            total += pow(alt[d] - media, 2);
        }
        dp = sqrt(total / numJogadores);
        printf("O desvio padrao eh: %.2f \n", dp);
        total = 0;
        }
        break;

    case 4:
        printf("===== OPCAO 4 SELECIONADA ===== \n");
        maior = alt[0];
        for( i=0; i< 10;i++) {
            if(alt[i] > maior){
                maior = alt[i];
                strcpy(nomeMaior, jogadores[i]);
              }
            }
            menor = alt[0];
            for(i=0; i < 10;i++){
                if(alt[i] < menor){
                  menor = alt[i];
                  strcpy(nomeMenor, jogadores[i]);
                }
            }
            printf("Jogador mais alto: %s , sua altura: %.2f \n", nomeMaior, maior);
            printf("Jogador mais baixo: %s , sua altura: %.2f \n", nomeMenor, menor);
        break;
    case 5:
        printf("===== OPCAO 5 SELECIONADA ===== \n");
        for(k = 1; k<n; k++){
        for(j = 1; j < n - 1; j++){
            if( alt[j]> alt[j+1]){
                    strcpy(tempNome, jogadores[j]);
                        strcpy(jogadores[j], jogadores[j+1]);
                            strcpy(jogadores[j+1], tempNome);
                aux = alt[j];
                alt[j] = alt[j+1];
                alt[j+1] = aux;
            }
        }
        }
        mediana = (alt[4]+ alt[5])/2;
        printf("mediana %.2f", mediana);
        break;
    case 6:
        printf(" Programa Encerrado \n");
        return 0;
        }
    }
    }

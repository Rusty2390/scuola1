//*cammarere gabriele 1s inf3 
#include <stdio.h>

int main() {
    int num[5];
    int i, j;
    int min, max, temp;
    float media = 0;
    int duplicati = 0;

    // Input dei numeri
    for(i = 0; i < 5; i++) {
        do {
            printf("Inserisci un numero positivo minore di 100: ");
            scanf("%d", &num[i]);
        } while(num[i] <= 0 || num[i] >= 100);
    }

    // Calcolo min, max e media
    min = max = num[0];
    for(i = 0; i < 5; i++) {
        if(num[i] < min) min = num[i];
        if(num[i] > max) max = num[i];
        media += num[i];
    }
    media /= 5;

    // Ordinamento (bubble sort)
    for(i = 0; i < 4; i++) {
        for(j = i + 1; j < 5; j++) {
            if(num[i] > num[j]) {
                temp = num[i];
                num[i] = num[j];
                num[j] = temp;
            }
        }
    }

    // Numero centrale (dopo ordinamento)
    int centrale = num[2];

    // Verifica duplicati
    for(i = 0; i < 5; i++) {
        for(j = i + 1; j < 5; j++) {
            if(num[i] == num[j]) {
                duplicati = 1;
            }
        }
    }

    // Output con switch
    for(i = 1; i <= 5; i++) {
        switch(i) {
            case 1:
                printf("Numero più piccolo: %d\n", min);
                break;
            case 2:
                printf("Numero più grande: %d\n", max);
                break;
            case 3:
                printf("Media: %.2f\n", media);
                break;
            case 4:
                printf("Numero centrale: %d\n", centrale);
                break;
            case 5:
                if(duplicati)
                    printf("Sono presenti numeri duplicati\n");
                else
                    printf("Non ci sono numeri duplicati\n");
                break;
        }
    }

    return 0;
}


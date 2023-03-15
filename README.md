// CÓDIGO FEITO POR SAMUEL DE JESUS CARVALHO PIRRHO;

#include <stdio.h>
#include <stdlib.h>

int main(){
	
	int NxN;
	int multiplicador;
	
	printf("enter a number to NxN: ");
	scanf("%d", &NxN);
	
	printf("enter a multiplier: ");
	scanf("%d", &multiplicador);
	
	int* mod(int array[NxN][NxN]){
		int x = 0;
		for(x; x < NxN; x++){
			int y = 0;
			for(y; y < NxN; y++){
				int valueXY;
				printf("enter a value to X: %d, Y: %d: ", x, y);
				scanf("%d", &valueXY);
				array[x][y] = valueXY;
			}
		}
		return *array;
	}
	
	void printArray(int array[NxN][NxN], int mult){
		switch(mult){
			case 1:
				printf("\t\t MATRIZ \n");
				break;
			case -1:
				printf("\t\t MATRIZ OPOSTA \n");
				break;
			default:
				printf("\t\t MATRIZ * %d \n", mult);
				break;
		}
		
		int x = 0;
		for(x; x < NxN; x++){
			int y = 0;
			for(y; y < NxN; y++){
				char *str;
				str = (y < NxN - 1) ? ", " : "\n";
				printf("\t\t %d %s", array[x][y] * mult, str);
			}
		}
	}
	
	int array[NxN][NxN];
	mod(array);
	
	printArray(array, 1);
	printf("\n");
	printArray(array, -1);
	printf("\n");
	printArray(array, multiplicador);
	printf("\n");
	
	return 0;
}

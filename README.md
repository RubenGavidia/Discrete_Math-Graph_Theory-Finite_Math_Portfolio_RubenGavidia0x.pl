# Discrete_Math-Graph_Theory-Finite_Math_Portfolio_RubenGavidia0x.pl
Logic, Set Theory, Number Theory, Combinatorics, Finite Mathematics, Graph Theory, Digital Geometry, Algorithmics, Information Theory, Computability and Complexity, Elementary Probability Theory, Linear Algebra, Functions, Markov Chains, Relations, Proofs, Partially Ordered Set.

RECURRENCE PROJECT: RESOLUTION OF THE GAME OFTHE TOWER OF HANOI

Implementation of a program in code (C language) that displays the numberof steps remaining to solve the juice of the towers of Hanoi, givenany position

The problem was solved by means of a code made in the language ofC programming, you can see how the problem can be divided intomultiple (one or more) instances of the same problem, applying recursion. Theprogram asks the user to choose which tower they want to start with (first,second or third tower), one of the auxiliary towers was called which is the firstthat will have the first mobilized disk, and the other remaining tower is the one that will haveall discs sorted as at the beginning. The function was calledhanoi , with rook1 , aux, and rook3 as parameters. The program has two parts what is known as recursion. The first part is to do theprocedure if you have 1 disc. The second part if you have more than one disc.The program will show each step performed and in each one the position of eachone of the towers. The number of steps to solve the problemit growsexponentially as the number of disks increases and this number ofsteps from n disks is given by the following formula 2 n -1. A waysimple to know if it is possible to finish the "game" is that if the amount ofdisks is odd, the initial piece will go to destination and if it is even, to auxiliary.

```
#include <stdio.h>
#include <stdlib.h>   
 
#define TORRE_INICIAL 1
#define TORRE_AUXILIAR 2
#define TORRE_FINAL 3
 
int hanoi(int numDiscos, int torreInicial, int torreAuxiliar, int torreFinal);
void muestra();
 
int t1=0,t2=0,t3=0,i,maxdiscos;
char disko='O';
 
int main()
{
    int cantDiscos, movimientos,seleccion;
 printf("Cantidad de discos a mover: ");
 scanf("%d", &cantDiscos);
 printf("\nPor cual torre iniciara el juego, torre 1, torre 2 o torre 3? (Ingrese solo el numero de torre): ");
 scanf("%d", &seleccion);
 printf("\n_________________________________________ \n");
  
 if(seleccion == 1){	 
 	t1=cantDiscos;
 	maxdiscos = cantDiscos;
 	printf("La Torre:\n");
 	muestra();
 	printf("\n_________________________________________\nLa serie de movimientos a realizar es:\n");
 	movimientos = hanoi(cantDiscos, TORRE_INICIAL, TORRE_AUXILIAR, TORRE_FINAL);
 	printf("\n\nSe realizaron en total %d movimientos\n", movimientos);
 	return 0;}

 else if(seleccion == 2){	 
 	t2=cantDiscos;
 	maxdiscos = cantDiscos;
 	printf("La Torre:\n");
 	muestra();
 	printf("\n_________________________________________\nLa serie de movimientos a realizar es:\n");
 	movimientos = hanoi(cantDiscos, TORRE_AUXILIAR, TORRE_INICIAL, TORRE_FINAL);
 	printf("\n\nSe realizaron en total %d movimientos\n", movimientos);
 	return 0;}

else if(seleccion == 3){	 
 	t3=cantDiscos;
 	maxdiscos = cantDiscos;
 	printf("La Torre:\n");
 	muestra();
 	printf("\n_________________________________________\nLa serie de movimientos a realizar es:\n");
 	movimientos = hanoi(cantDiscos, TORRE_FINAL, TORRE_AUXILIAR, TORRE_INICIAL);
 	printf("\n\nSe realizaron en total %d movimientos\n", movimientos);
 	return 0;}

 else{
	printf("Error. Introdujo un numero diferente a 1, 2 y 3\n");
	return 1;}
}
 
int hanoi(int numDiscos, int torreInicial, int torreAuxiliar, int torreFinal)
{
    static int movimientos = 0;
 if(numDiscos == 1) // solo hay un disco
 {
  printf("\n\n%d)Mover el disco superior de la torre %d a la torre %d\n", movimientos+1, torreInicial, torreFinal);
  movimientos++;
 
        if(torreInicial==1)
            t1--;
        if(torreInicial==2)
            t2--;
        if(torreInicial==3)
            t3--;
        if(torreFinal==1)
            t1++;
        if(torreFinal==2)
            t2++;
        if(torreFinal==3)
            t3++;
 
  muestra();
 }
 else // mas de un disco
 {
//recursividad: llama a la misma funcion nuevamente
  hanoi(numDiscos - 1, torreInicial, torreFinal, torreAuxiliar);
  printf("\n\n%d)Mover el disco superior de la torre %d a la torre %d\n", movimientos+1, torreInicial, torreFinal);
  movimientos++;
 
        if(torreInicial==1)
            t1--;
        if(torreInicial==2)
            t2--;
        if(torreInicial==3)
            t3--;
        if(torreFinal==1)
            t1++;
        if(torreFinal==2)
            t2++;
        if(torreFinal==3)
            t3++;
 
  muestra();
  hanoi(numDiscos - 1, torreAuxiliar, torreInicial, torreFinal);
 }
 return movimientos;
} 
 
void muestra(){
    printf("\n\tTorre1:");
 for(i=1;i<=t1;i++){
        printf("%c",disko);
 }
    printf("\n\tTorre2:");
 for(i=1;i<=t2;i++){
        printf("%c",disko);
 }
    printf("\n\tTorre3:");
 for(i=1;i<=t3;i++){
        printf("%c",disko);
 }
}


```

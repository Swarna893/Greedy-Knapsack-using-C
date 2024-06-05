# Greedy-Knapsack-using-C


#include <stdio.h>
int i, p[7], w[7],M;
float pwindex[7];

int GreedyKnapsack(int M){
    float P=0.0, x[i];
    int profitmat[7];
    for(i=0;i<7;i++){
        x[i]=0.0;
    }
    float U=M;
    for(i=0;i<7;i++){
        if(w[i]>U){
            break;
        }
        else{
          x[i]=1.0;
          U=U-w[i];
          P=P+p[i];  
        }
    }
    if(i<=7){
        x[i]=U/w[i];
        P=P+p[i]*x[i];
    }
    printf("\n\nTotal profit: %0.2f", P);
    printf("\n\n");
    printf("The solution vector: \n");
    for(i=0;i<7;i++){
        printf("%0.2f ", x[i]);
    }

}

int main() {
    // Write C code here

    for(i=0;i<7;i++){
        printf("profit %d: ", i+1);
        scanf("%d", &p[i]);
        printf("weight %d: ", i+1);
        scanf("%d", &w[i]);
    }
    printf("\n\nEnter the size of the knapsack: ");
    scanf("%d", &M);

    printf("\n\n\n");

    // int p[7]={90,60,20,40,70,30,50};
    // int w[7]={5,5,2,5,14,10,25};
    printf("The profit weight index: \n");
    for(i=0;i<7;i++){
        pwindex[i]=p[i]/w[i];
        printf("%0.2f ", pwindex[i]);
    }
    GreedyKnapsack(M);
    // printf("\n\nThe maximized profit is: %d", P);

    // print("The profit array is: ");
    // for(i=0;i<7;i++){
    //     print("%d", p[i]);
    // }
    // print("The wigh array is: ");
    // for(i=0;i<7;i++){
    //     print("%d", p[i]);
    // }


    return 0;
}

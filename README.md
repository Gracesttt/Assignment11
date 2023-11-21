# Assignment11
#include <stdio.h>
#define SIZE 300

struct student{
        char name[20];
        double score;
        char grade;
    };
    
int getStudent(struct student []);
void convertGrade(struct student cst[],int);
void Highest(struct student cst[],int);
    
int main()
 {
     struct student cst[SIZE];
     int i, max,n;
     n=getStudent(cst);
     convertGrade(cst,n);
     
     for(i=0;i<n;i++){
     printf("Name:%s Score:%.2lf Grade:%c\n",cst[i].name, cst[i].score, cst[i].grade);
     }
     
    Highest(cst,n);
    return 0;
 }

int getStudent(struct student x[]){
    int i,n;
    printf("How many students do you want(Max=%d)?",SIZE);
    scanf("%d",&n);
    for(i=0;i<n;i++){
     printf("Input name %d:",i+1);
     scanf("%s",x[i].name);
     printf("Score:");
     scanf("%lf",&x[i].score);
    
} return n;
}

void convertGrade(struct student cst[],int n){
    int i;
    for(i=0;i<n;i++){
    if(cst[i].score >= 80 ) cst[i].grade='A';
    else if (cst[i].score >= 70 ) cst[i].grade='B';
    else if (cst[i].score >= 60 )  cst[i].grade='C';
    else cst[i].grade='F';
 }
}


void Highest(struct student cst[],int n){
    int i;
    int max=0;
    for(i=0;i<n;i++){
        if(max < cst[i].score) max=cst[i].score;
    }
    
    for(i=0;i<n;i++){
        if(cst[i].score==max) printf("%s got maximum score: %.2lf and grade %c",cst[i].name,cst[i].score,cst[i].grade);
    }
   
}


 
#include<stdio.h> 
#include<conio.h> 
struct fcfs{ 
    int pid; 
    int btime; 
    int wtime; 
    int ttime; 
} p[10]; 
void main() 
{ 
    int i,n; 
    int totwtime=0; 
    int totttime=0; 
    printf("\nFCFS scheduling "); 
    printf("\nenter the no of processes:"); 
    scanf("%d",&n); 
    for(i=0;i<n;i++) 
{ 
    p[i].pid=i+1; 
    printf("burst time of process %d:",p[i].pid); 
    scanf("%d",&p[i].btime); 
} 
    p[0].wtime=0; 
    p[0].ttime=p[0].btime; 
    for(i=1;i<n;i++) 
    { 
        p[i].wtime=p[i-1].wtime+p[i-1].btime; 
        p[i].ttime=p[i].wtime+p[i].btime; 
        totttime+=p[i].ttime; 
        totwtime+=p[i].wtime; 
    } 
     
    printf("\nTotal waiting time: %d\n", totwtime); 
    printf("Average waiting time: %d\n", totwtime/ n); 
    printf("Total turnaround time: %d\n", totttime); 
    printf("Average turnaround time: %d\n", totttime / n); 
getch(); 
} 
 
  
OUTPUT: 
 
FCFS scheduling  
enter the no of processes:3 
burst time of process 1:24 
burst time of process 2:3 
burst time of process 3:3 
 
Total waiting time: 51 
Average waiting time: 17 
Total turnaround time: 57 
Average turnaround time: 19

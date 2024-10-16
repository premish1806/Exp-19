# Exp-19

## Aim:
To implement a queue data structure using an array in C++ and perform basic queue operations such as enqueue, dequeue, and display.

## Software Used:
- Dev c++
  
## Theory:
A queue is a linear data structure that operates on the First In, First Out (FIFO) principle, meaning the element added first is the one to be removed first. The primary operations are enqueue (to add an element at the rear) and dequeue (to remove an element from the front). The program implements a static queue using an array with a fixed size and handles both full and empty queue conditions. Queues are used in various real-world scenarios such as task scheduling, buffering, and handling requests in a sequential manner.

## Program 1: Queue Implementation
<strong> Code: </strong>
<br>
```cpp
// Premish Ninawe
// 23070123092
// ENTC B1
#include <iostream>
using namespace std;
#define size 5
#define ERROR -9999
class Queue{
    int rear, front, ar[size];
    public:
    Queue(){
        rear = -1;
        front = -1;
        ar[0]=0;
    }
    void enqueue(int);
    int dequeue();
    void disp();
};
void Queue :: enqueue(int num){
    if (rear == (size+1)){
        cout<<"Queue is full"<<endl;
    }
    else{
        if(front == -1){
            ar[++front]=num;
            rear++;
        }
        else{
            ar[++rear]=num;
        }
    }
}
int Queue ::dequeue(){
    if(front ==-1 || front ==(rear+1)){
        cout<<"Queue is empty"<<endl;
        return ERROR;
    }
    else{
        int val = ar[front++];
        return val;
    }
}
void Queue :: disp(){
    if(front ==-1 || front ==(rear+1)){
        cout<<"Queue is empty"<<endl;
        return;
    }
    else{
        int i = front ;
        while (i!=(rear+1)){
            cout<<ar[i];
            i++;
        }
    }
}

int main(){
        Queue q1;
        q1.enqueue(4);
        q1.enqueue(8);
        q1.enqueue(3);
        q1.disp();
        int val = q1.dequeue();
        cout<<endl<<"Deleted element: "<<val<<endl;
        q1.disp();
}

```
<strong> Output: </strong>
<br>
![image](https://github.com/user-attachments/assets/034e2c8e-af8c-4fef-aaf0-3a944430e34e)

## Conclusion:
This program demonstrates the basic working of a queue using a fixed-size array in C++. It successfully handles operations like enqueue, dequeue, and display. The queue operates on the FIFO principle, and the program checks for both full and empty conditions, providing relevant feedback. This implementation highlights the practical use of queues in scenarios where sequential data processing is required.

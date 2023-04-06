// StackArray
//Implementing a Stack with the use of arrays
#include <iostream>
#include <chrono>
using namespace std;
using namespace std::chrono;

#define SIZE 10
int arr[SIZE];
int top = -1;

bool isEmpty()
{
  if(top==-1)
  return true;
  else
  return false;
}


void Pop()
{
 if(isEmpty())
  cout<<"Stack Underflow"<<endl;
 else
  top--;
}

void StackTop()
{
 if(isEmpty())
  cout<<"Stack is empty!"<<endl;
 else
  cout<<"Element at top is: "<<arr[top]<<endl;

}

void isFull() {
    if(top==SIZE-1)
  {    cout<<"Stack Overflow"<<endl;
        exit(1);
  }
}


void Push(int value)
{
  isFull();


  top++;
  arr[top]=value;

}

void Display()
{
  if(isEmpty())
 {
    cout<<"Stack is empty"<<endl;
 }
 else
 {
  for(int i=0 ; i<=top; i++)
    cout<<arr[i]<<" ";
   cout<<endl;

  }

}

int main()
{

auto start = high_resolution_clock::now();


 Push(8);
Push(10);
Push(5);
Push(11);
Push(15);
Push(23);
Push(6);
Push(18);
Push(20);
Push(17);
Display();
Pop();
Pop();
Pop();
Pop();
Pop();
Display();
Push(4);
Push(30);
Push(3);
Push(1);
Display();

auto stop = high_resolution_clock::now();

auto duration = duration_cast<microseconds>(stop - start);

    cout << "Time taken by function: "
         << duration.count() << " microseconds" << endl;

}

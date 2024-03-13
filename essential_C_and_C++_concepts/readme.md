# Basic C and C++ Concepts.
#### 1. Arrays<br>2. Structure<br>3. Pointers<br>4. Reference<br>5. Parameter Passing<br>6. Classes<br>7. Constructor<br>8. Templates

## Arrays 
#### Group of elements at same place under single name.
#### Array declaration and initialisation :
    int Arr[5]; 
    Arr[0]=4;

    int B[3]={1,2,3};
##### Note : Its saved in stack area of memory.....

## Structures
#### Group of diffrent similar data under same name. It is a user defined datatype.
#### Declaration and Declaration

    struct Rect {
        int length;
        int breath;
    }

##### Note : size of it is equal to total of indivdual of each member.

    int main(){
        struct Rect r;
        struct rect r={10,5};

        r.length = 15;
    }

## Pointer 
#### It is a variable that is used to store addresses and if you think why we need to do so, It is to access any variable indirectly. Why we need to access any variable indirectly, if we want to access the heap storage we have to like that only....

#### Declaration and dereferencing
    int a=10;
    int *p;
    p=&a; // the space it will take is 2 only.
    cout<<*p; // dereferencing

#### Accessing Heap using pointer to declare arrays
    int *p;
    p=(int*)malloc(5*sizeof(int));
    
    p=new int[5];

## Reference
#### Its only present in C++ not in C. Its just anothe name given to a variable.

    int a=10;
    int &r=a;

## Pointer to Structure 
    struct rect{
        int length;
        int breath;
    }

    int main(){
        struct rect a ;
        int *p=&a;
        p->length=10;
        p->breath=5;
    }
#### Dynamic :
    struct rect{
        int length;
        int breath;
    }

    int main(){
        struct rect *p;
        p=(struct rect(*)malloc(sizeof(struct rect)));
    }

## Function
#### The piece of code that perform a specific task.(Modular or procedual programming.)
    int add(int a,int b){
        return a+b;
    }

    int main(){
        int x,y;
        x=10;
        y=20;
        cout<<add(x,y);
        return 0;
    }
#### Parameter passing methods
#### 1. Pass by values<br>2. Pass by address<br>3. Pass by reference

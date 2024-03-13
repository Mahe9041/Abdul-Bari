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

#### pass by value:
    
    void print(int a){
        cout<<a;
    }
    void main(){
        int a;
        a=5;
        print(a);
    }

#### Pass by address:

    void swap(int *a,int *b){
        int temp=*a;
        *a=*b;
        *b=temp;
    }

    void main(){
        int a=10,b=1;
        swap(&a,&b);
    }

#### Pass by reference:

    void swap(int &a,int &b){
        int temp=a;
        a=b;
        b=temp;
    }

    void main(){
        int a=10,b=1;
        swap(a,b);
    }

## Array as parameter
    void printArr(int a[],int n){
        for(int i=0;i<n;i++){
            cout<<a[i]<<" ";
        }
    }

    void main(){
        int a[5]={1,2,3,4,5};
        printArr(a);
    }

##### Note : The arrays are always pass by address only.

    int* passingArray(int size){
        int *p;
        p=(int*)malloc(size*sizeof(int));
        for(int i=0;i<size;i++){
            p[i]=i+1;
        }
        return p;
    }

    void main(){
        int s=5;
        int *p=passingArray(5);
        for(int i=0;i<s;i++){
            cout<<p[i]<<" ";
        }
    }

## Structure as parameter
#### Pass by value
    struct rect{
        int length;
        int breath;
    }

    void passStructure(struct rect a){
        cout<<a.length;
        cout<<a.breath;
    }

    void main(){
        struct rect r={12,13};
        passStructure(r);
    }
##### Note : The pass by reference is exactly the same as pass by value just the '&' added.
#### Pass by address
    struct rect{
        int length;
        int breath;
    }

    void passStructure(struct rect *a){
        cout<<a->length;
        cout<<a->breath;
    }

    void main(){
        struct rect r={12,13};
        passStructure(&r);
    }
## Converting C code to C++ code
#### 1 thing we have to keep in mind that structure is user defined datatype and groping of variable having same work. Now for structure we have to define additional functions so to avoide that we have classes and objects. Class is user defined data type which is collection of variables and member functions.

    struct rect{
        int length;
        int breath;
    }

    void initialise(struct rect &r1,int length, int breath){
        r1.length=length;
        r1.breath=breath;
    }

    void area(struct rect &r1)
    {
        return r1.length*r1.breath;
    }

    void main(){
        struct rect r;
        initialise(r,10,1);
        area(r)
    }

#### Now the above in class
    class rect{

        private:
        int length;
        int breath;

        public:
        Rect (int length, int breath) //constructor
        {
            this.length=length;
            this.breath=breath;
        }

        void area()
        {
            return length*reath;
        }
    };

    void main(){
        rect r{10,1}; //object
        
        r.area(r)
    }

## Class and constructor
    #include<iostrem.h>
    using namespace std;
    class Rect{
        private:
        int length;
        int breath;
        public:
        Rect(){
            length=breath=1;
        }
        Rect(int l,int b);
        int area();
        int perimeter();
        int getLength(return length);
        void setLength(int l){
            length=l;
        }
        ~Rect();
    };

    Rect :: Rect(int l,int b){
        length =l;
        breath =b;
    }
    int Rect::area(){
        return length*breath;
    }
    int Rect::perimeter(){
        return 2*(length+breath);
    }
    Rect::~Rect(){}

    int main(){
        Rect r(10,5);
        cout<<r.area();
        cout<<r.perimeter();
        r.setlength(20);
        cout<<r.getlength();
    }
## Template class
#### this topic is not that touched in the course so can be skipped.
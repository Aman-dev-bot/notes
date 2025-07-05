
- It requires a base case so it does not goes for infinity.
- Recursion means a function calling itself.  

###### There are different types of Recursions.
1. Tail recursion.
2. Head recursion.
3. Tree recursion.
4. Indirect recursion.
5. Nested recursion. 
---
## Tail Recursion 

code example.

```
#include <stdio.h>

void func(int n){
 if(n < 0){
 printf("%d", n);
 func(n -1);
 };
}

int main(){
int a = 3;
func(a);
}

```

Visual Representation if the stack trace

```

	Call 1->   func(3)  //output: 3, Operation func(3-1) 
				  ↓
	Call 2->   func(2)  //output: 2, Operation func(2-1) 
				  ↓
	Call 3->   func(1)  //output: 1, Operation func(1-1) 
				  ↓
	Call 4->   func(0)  //Operation terminates 

A total of 4 activation records were made 
``` 

A tail recursion can often be easily substituted by a loop most of the time.

```
#include <stdio.h>

void func(int n){
 while(n < 0){
 printf("%d", n);
 n--;
 };
}

int main(){
int a = 3;
func(a);
}
```

Difference between Recursion and loop in Tail recursion context.

```
|-----------------------------------------------------------------------------------|
| Tail recursion                           | Loops                                  |
|                                          |                                        |
| 1. A tail recursive fn will be slower    |1. A loop is faster than tail recursion |
|    than a loop.                          |2. It has a time complexity of o(1)     |
| 2. As the it has time complexity of o(n) |   as only one activation reord is made |
|    since it creates 4 activation records |3. many compilers will convert tail rec-|
|    in the example o(4)                   |  -sion to a loop.                      |
|-----------------------------------------------------------------------------------|

``` 

---
## Head Recursion 

code example.

```
#include <stdio.h>

int func(int n){
static int x = 0;
 if(n < 0){
 x++;
 return func(n-1) + x;
 };
 return 0;
}

int main(){
int a = 3;
func(a);
}

```

Visual Representation if the stack trace

```
//x will be called on return
	Call 1->   func(3) -> on return x = 3 //output
				  ↓
	Call 2->   func(2) -> on return x = 3 //output
				  ↓
	Call 3->   func(1) -> on return x = 3 //output
				  ↓
	Call 4->   func(0)    

A total of 4 activation records were made 
``` 

A tail recursion can be substituted by a loop however the function will require some changes.

```
#include <stdio.h>

void func(int n){
 while(n < 0){
 printf("%d", n);
 n--;
 };
}

int main(){
int a = 3;
func(a);
}
```



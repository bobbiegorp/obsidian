A pointer in [[C|C]] is simply a variable (piece of memory) whose value is the address (location) of another piece of memory. Below the variable a is declared as an int with value 4 and pA is a pointer to the address of variable a, denoted by &a. The type of pA is integer pointer.

```
int a = 4;
int *pA = &a;
```

If you have a pointer to an address and want to retrieve the value that is actually stored at that address, you can retrieve that using the dereference operator asterisk. The line below will print the value located at the address denoted by pA.

```
printf("%d\n", *pA);
```

Because different datatypes have different sizes in memory - a different number of bytes - the compiler needs to know what the datatype is of the value located at pA, so that can retrieve the correct number of bytes. An int is stored as 4 bytes by the most common compilers,  and because pA is specifically of type integer pointer, 4 bytes of memory will be retrieved starting from the address pA.

#### Void pointers

There is also the concept of a void pointer, i.e. a pointer pointing at a memory location of unspecified size.  The code below assigns the address of a to vA, which is of type void pointer. 
```
int a = 4;
void *vA = &a;
printf("%d\n", *vA);
```

In the print statement, we are trying to dereference vA, but since it is of type void pointer, the compiler does not know how many bytes to retrieve and the code will not compile.

The heap memory allocation functions malloc, calloc, realloc and free all work with void pointers. Malloc for example returns a void pointer and free takes a void pointer as parameter. This is because C gives you the freedom to tell the compiler what type is stored at a specific address. You don't tell malloc to reserve an Person struct on the heap, but you tell it to reserve a number of bytes on the heap and you then tell the compiler that it is actually a Person struct stored at that address.

```
typedef struct {
	int id;
	char name[64];
} Person;

// Implicit type cast of void pointer to int pointer, may fail depending on compiler settings
Person *pPerson = malloc(sizeof(Person));

// Explicit type casting is what should be used
Person *pPerson = (Person*)malloc(sizeOf(Person));
```

The memory needs to be freed up using the free function, which takes a void pointer as input, but here we can pass in pPerson without explicit type casting.

```
free(pPerson);
```

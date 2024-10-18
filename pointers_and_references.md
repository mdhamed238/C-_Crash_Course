
# C++ Pointers and References Cheatsheet

## Key Definitions

- **Pointer**: A variable that stores the memory address of another variable.
- **Reference**: An alias for another variable. It cannot be null or reassigned after initialization.

### Main Differences
- **Pointers** can be reassigned and can be `nullptr`. They require dereferencing to access the value they point to.
- **References** cannot be reassigned or null, and they automatically dereference.

## Syntax

### Pointer
```cpp
int* ptr;            // Declaration
ptr = &variable;     // Initialization with the address of 'variable'
*ptr = 10;           // Dereferencing to assign a value
```

### Reference
```cpp
int& ref = variable; // Declaration and initialization (must be at the same time)
ref = 20;            // Using the reference
```

## Pointer Operations

### Dereferencing
```cpp
int x = 5;
int* ptr = &x;
*ptr = 10; // Changes the value of x to 10
```

### Null Pointers
```cpp
int* ptr = nullptr; // Pointer that points to nothing
```

### Pointer Arithmetic
```cpp
int arr[3] = {1, 2, 3};
int* ptr = arr;
ptr++; // Now ptr points to arr[1]
```

## References

### Const Reference
```cpp
const int& ref = variable; // Reference to a constant, cannot modify the variable through the reference
```

### Differences from Pointers
- References must be initialized when declared.
- They are not reassignable, unlike pointers.
- No need for explicit dereferencing with references.

## Examples

### Pointer to an Integer
```cpp
int x = 5;
int* ptr = &x;
```

### Reference to an Integer
```cpp
int x = 5;
int& ref = x;
```

### Pointer Arithmetic
```cpp
int arr[3] = {1, 2, 3};
int* ptr = arr;
ptr++; // Pointer now points to arr[1]
```

### Function Taking a Pointer
```cpp
void increment(int* ptr) {
    (*ptr)++;
}
```

### Function Taking a Reference
```cpp
void increment(int& ref) {
    ref++;
}
```

## Best Practices

- **Always initialize pointers**: Uninitialized pointers can cause undefined behavior.
- **Use `nullptr` instead of `NULL`**: It is safer and more modern.
- **Avoid pointer arithmetic unless necessary**: It can lead to errors and make code harder to read.
- **Prefer references over pointers when you don’t need nullability or reassignment**: They are simpler and safer.
- **Use `const` wherever possible**: This helps avoid accidental modifications.

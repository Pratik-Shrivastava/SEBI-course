# ☕ Section 1 – Java Programming Concepts

## 1. Program Control (Iteration, Recursion, Functions)
**Definition:** Program control refers to how instructions are executed in sequence or selectively using loops, decisions, or recursion.

**Concept:** In Java, control flow ensures logical execution using:
- **Decision-making:** `if`, `switch`
- **Iteration:** `for`, `while`, `do-while`
- **Recursion:** Method calling itself

**Examples:**
```java
for(int i=1; i<=5; i++)
  System.out.println("Number: " + i);

int factorial(int n) {
  if(n == 0) return 1;
  return n * factorial(n - 1);
}
```
👉 `for` executes sequentially; recursion repeats with a base condition.

**Practice:**
- Write recursive Fibonacci.
- Print multiplication table using `while`.

**MCQs:**
- Executes at least once → ✅ do-while  
- Recursive functions need → ✅ Base condition  
- `continue` skips iteration → ✅ True

---

## 2. Scope of Variables
**Definition:** Defines where a variable can be accessed.

**Types:**
- **Local:** Inside method/block
- **Instance:** Non-static, per object
- **Class/Static:** Shared by all objects

**Example:**
```java
class Demo {
  static int count = 0;  // Class scope
  void show() {
    int x = 10;          // Local scope
    count++;
  }
}
```
👉 `x` exists only inside `show()`; `count` persists across instances.

---

## 3. Binding of Variables & Functions
**Definition:** Linking function or variable to its definition.

**Types:**
- **Static Binding:** Compile-time (method overloading)
- **Dynamic Binding:** Runtime (method overriding)

**Example:**
```java
class A { 
  void display() { 
    System.out.println("A"); 
  }
}

class B extends A { 
  void display() { 
    System.out.println("B"); 
  }
  public static void main(String[] args) {
    A obj = new B();
    obj.display(); // B
  }
}

```
👉 Bound dynamically at runtime.

---

## 4. Parameter Passing
**Concept:** Java passes parameters **by value**. For objects, the **reference value** is copied.

**Example:**
```java
void change(int x) {
  x = 10;
}
int num = 5;
change(num); // num = 5
```
👉 Copy passed → original unchanged.

---

## 5. Functional & Logic Programming
**Functional Programming (Java 8+):** Uses **lambdas** and **streams**.
```java
List<Integer> list = Arrays.asList(1,2,3,4);
list.forEach(n -> System.out.println(n));
```
👉 `->` defines an inline function.

**Logic Programming:** Simulated via tools like **Drools** or **Prolog bridges**.

---

## 6. OOP Concepts
| Principle | Description |
|------------|-------------|
| Encapsulation | Wrapping data & methods using private fields |
| Abstraction | Hiding complexity (abstract/interface) |
| Inheritance | Reuse from base class |
| Polymorphism | Same name, different behavior |

**Example:**
```java
abstract class Shape { 
  abstract void draw(); 
}
class Circle extends Shape { 
  void draw() { 
    System.out.println("Circle"); 
  } 
}
```

---

## 7. Inheritance
**Types:**
- Single
- Multilevel
- Hierarchical

**Example:**
```java
class A {

}
class B extends A {

}
class C extends B {

}
```
👉 `C` inherits all from `A` and `B`.

---

## 8. Class & Object
**Syntax:**
```java
class Car {
  String brand;
  void drive(){ 
    System.out.println(brand + " driving"); 
  }
}
Car c = new Car();
c.brand = "Tesla";
c.drive();
```
👉 Class = blueprint; Object = instance.

---

## 9. Constructors
| Type | Description |
|------|--------------|
| Default | Auto-created |
| Parameterized | Accepts args |
| Copy | Clones another |

**Example:**
```java
Car(String b){ brand = b; }
```

---

## 10. Exception Handling
**Definition:** Handles runtime errors using `try-catch-finally`.
```java
try {
  int x = 5/0;
} catch(ArithmeticException e) {
  System.out.println("Error: "+e);
} finally {
  System.out.println("Completed");
}
```
👉 `finally` always executes.

---

### 🧩 Revision Table (Java)
| Concept | Keyword/Class |
|----------|----------------|
| Dynamic Binding | Overriding |
| OOP Parent | Object |
| Exception Base | Throwable |
| Default Access | Package-private |
| Abstract Method | abstract |

---

### 💡 Exam Tips
- Objects passed by **reference copy**, not by reference.  
- Only **unchecked exceptions** are optional to catch.  
- Constructors **cannot return** values.  
- Interfaces support **multiple inheritance**.  

---

# 💻 Section 2 – C Programming Concepts

## 1. Program Control
**Definition:** Manages flow using loops/conditions.
```c
for(int i=0;i<5;i++) printf("%d ",i);

int fact(int n){ if(n==0) return 1; return n*fact(n-1); }
```

---

## 2. Scope of Variables
| Scope | Lifetime | Example |
|--------|-----------|----------|
| Local | Inside function | `{ int x=10; }` |
| Global | Whole program | `int x;` |
| Static | Retains value | `static int count;` |
| Register | CPU stored | `register int i;` |

---

## 3. Binding
**Static only** → compile-time.

---

## 4. Parameter Passing
| Type | Example |
|-------|----------|
| By Value | Copy passed |
| By Reference | Via pointer |

```c
void swap(int *a,int *b){int t=*a;*a=*b;*b=t;}
```

---

## 5. Functions
Reusable blocks with recursion and prototypes.

---

## 6. Exception Handling
No native system → use return codes or `setjmp()/longjmp()`.

### 🧩 Revision Table (C)
| Concept | Feature |
|----------|----------|
| Binding | Static |
| Inheritance | ❌ |
| Param Passing | Value/Pointer |
| Memory | malloc()/free() |
| Error Handling | Manual |

💡 **Tips:** Always free memory; recursion uses stack.

---

# 🧩 Section 3 – C++ Programming Concepts

## 1. Program Control
```cpp
for(int i=0;i<5;i++) cout<<i;
```
Recursion works same as C.

---

## 2. Scope of Variables
```cpp
class Demo { int x; public: void set(){x=10;} };
```

---

## 3. Binding
| Type | Mechanism | Example |
|------|------------|----------|
| Static | Overloading | Compile time |
| Dynamic | Virtual | Runtime |

```cpp
class A { public: virtual void show(){cout<<"A";} };
class B:public A{ void show(){cout<<"B";} };
A *p=new B; p->show();
```

---

## 4. Parameter Passing
| Method | Example |
|---------|----------|
| By Value | `void f(int x)` |
| By Reference | `void f(int &x)` |
| By Address | `void f(int *x)` |

---

## 5. Functional Programming
```cpp
auto add=[](int a,int b){return a+b;};
cout<<add(2,3);
```

---

## 6. OOPS Concepts
Four pillars → Encapsulation, Abstraction, Inheritance, Polymorphism.

---

## 7. Inheritance
Supports **multiple inheritance**.
```cpp
class A{}; class B{}; class C: public A, public B{};
```

---

## 8. Class & Object
```cpp
class Car{public:string brand; void drive(){cout<<brand;}};
```

---

## 9. Constructors
```cpp
Car(string b){brand=b;}
Car(const Car &c2){brand=c2.brand;}
```

---

## 10. Exception Handling
```cpp
try{ throw 1; } catch(int e){ cout<<"Error"; }
```

---

### 🧩 Revision Table (C++)
| Concept | Keyword |
|----------|----------|
| Dynamic Binding | virtual |
| Base Exception | exception |
| Memory | new/delete |
| Access | public/private/protected |
| Overloading | Compile-time |

💡 **Tips:** Use virtual in destructors; copy constructor handles duplication.

---

# 🧾 Final Revision Snapshot
| Topic | Java | C | C++ |
|--------|------|---|-----|
| Paradigm | OOP | Procedural | OOP + Procedural |
| Exception Handling | ✅ | ❌ | ✅ |
| Inheritance | ✅ | ❌ | ✅ |
| Binding | Static/Dynamic | Static | Static/Dynamic |
| Parameter Passing | By value (ref copy) | Value/Pointer | Value/Ref/Pointer |
| OOP Support | Full | None | Full |
| Functional | Lambdas (Java 8+) | ❌ | Lambdas |
| Memory Control | GC | Manual | new/delete |

---

### 🧠 Common Exam Pitfalls
- Java: Objects are **reference copies**,
# C/C++ k zapamatování

online C/C++ kompilátor (http://cpp.sh/)

## Práce s pamětí (rozpracované)

__Pro alokaci repektive dealokaci paměti používáme v C funkce `malloc()`/`free()`,
namísto toho v C++ kromě zmíněných C funkcí, operátory `new`/`delete`.__

__Před použitím jakéhokoliv surového ukazetele se ujisti, že je validní.__

```c
if (ptr != NULL) {
    // Dělěj něco s `ptr`.
}
```

V C++11 je definován typ `nullptr_t` jehož je `nullptr` ?konstantou? <s>instancí</s>. Preferujem
jeho použití před hodnotou NULL jak ji známe z C.

```c++
if (ptr != nullptr) {
    // Dělěj něco s `ptr`.
}
```

__Po uvolnění funkcí `free()` ukazatele ho explicitně nastav na hodnotu `NULL` respektive `nullptr`.__

```c
if (ptr != NULL) { // viz předhchozí pravidlo
    free(ptr);
    ptr = NULL;    // << (!)
    // assert()
}
```

__V C++ použijeme pro uvolnění paměti operátor `delete`.__ 

```c++
if (ptr != nullptr) {
    delete ptr;
    ptr = nullptr; // << (!)
}
```

__Pokud v C alokujeme paměť pomocí funkce `malloc()`, musíme zkontroloval, jestli se alokace povedla.__

```c
struct obj* ptr = malloc(sizeof(struct obj));
if (ptr != NULL) { 
    // ...
}
```

__V C++ se při nepovedené alokaci objektu pomocé operátoru `new` vyhodí výjimka `bad_alloc`.__

```c++ 
auto ptr = new Object(); // Object *ptr = new Object();
```

__Pokud nechceme vyhazovat výjimku `bad_alloc`, můžeme použít instanci `nothrow` typu `nothrow_t`, která je v hlavičkovém souboru `<new>`.__

```c++
#include <new>
struct C {};

int main() {    
    auto ptr = new (std::nothrow) C();    
}
```

Poznámka: `nothrow` nezabrání vyhození výjimek např, v konstruktoru `C`.

__Přetypování při použití malloc není nutné.__

```c    
struct node *n = (node*)malloc(sizeof(struct node));
```

__Alokaci paměti můžeme provést buď uvedením typu nebo dereferencování ukatele na typ.__

(TODO)

```c
malloc(sizeof(struct node))
malloc(sizeof(* node));
```

# C++ (zmatené poznámky)

Na jednoduchém bodu si můžeme ukázat několik základních konceptů C++, pro práci se strukturami a třídami.

Pro jednoduché demonstrační příklady si vytvoříme bod jako strukturu se dvěma 
atributy x, y, které reprezentují jeho souřadnice v euklidovském prostoru.

    struct Point { 
        double x, y; 
    };

Podobně bychom vytvářeli i strukturu v C, ale struktura v C++ se sémanticky liší od struktury v C v několika ohledech (porovnání s C na konci článku). 

Struktura v C++ je vlastně třída, jejíž všechny členské proměnné (případně metody) jsou veřejné, tedy označené modifikátorem `public`. Následující deklarace je tedy stejná jako první.

    class Point {
    public: double x, y;
    }

Případně tato verze, kdy členy deklarujeme jako soukromé, jsou stejné.

    class Point {           struct Point {
         double x, y;       private: double x, y;
    }                       } 

Dále budeme pro jednoduchost pracovat s první uvedenou strukturou a budeme 
se ptát, co se děje na pozadí, když kompilátor narazí na takovouto deklaraci struktury.

V tomto případě za nás kompilátor měl vytvořit následující věci:






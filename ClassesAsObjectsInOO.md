# Třida jako objekt v OO jazycích 

Mezi jazyky o kterých se tvrdí, že jsou OO  -- tedy obejtově orientované -- 
stavících nebo podporujících obejtově orienatované programpování jsou dvě skupiny.

První, která následuje Smalltalk je ta, kdy i sammotná třída je chápaána a reprezentována jako objekt
(Smallatalk, Python, Ruby) a druhá kde tomu tak není (C++, Java, C#).

Nicméně i Java umožnuje prozkoumat třídu instance pomocí třídy Class...

Můžeme upravit samotnou třídu! === Monkey patching; jestli je to dobrý nápad je druhá otázka!

    >>> class Foo(): pass
    >>> obj = Foo()
    >>> obj.x = "X"
    >>> obj.x
    'X'
    >>> Foo.y = "Y"
    >>> obj.y
    'Y'
    >>>

No a protože třída je prostě šablona pro třidu a třída je objektem, pak tu musí být šablonat pro šablonu --> tedy třída třídy 
a té říkáme metatřída --metaclass -- metatřída mění chování samotných tříd!

mataclass in Python: TODO
S
Měníme objekt (instanci třídy) za běhu:
    
    >>> class Bar(): pass
    >>> obj.__class__ = Bar()


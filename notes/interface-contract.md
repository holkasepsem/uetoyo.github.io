# Je rozhraní kontrakt?

Když jsem se usilovně snažil, při učení se objektově orientovaného programování pochopit
k čemu je rozhraní, pořád mi něco nesedělo. Často jsem četl, že rozhraní je kontrakt.
Moje otázka byla, když je rozhraní kontrakt, proč mi dovoluje ho porušovat?

	interface CanQuack() {
		String quack();
	}

    class Duck implements CanQuack {
        String quack() {
            return "woof";
        }
    }

Odpověd je překvapivě jednoduchá. Rozhraní je pouze syntaktický kontrak nikoliv sémantický.
Pokud chceme přidat sémantický kontrakt, musíme použít buď abstraktní třídu nebo trait.

Smaozřejmě, že rozhraní má své místo, jen je třeba se mít na paměti, že kromě syntaxe nevynucuje 
správné chování.

Koneckonců Design-By-Contract je samostatnou kapitolou, koukněte se na jazyk Eiffel nebo Ada 2012.

## Odkazy

http://blog.ploeh.dk/2010/12/02/Interfacesarenotabstractions/
https://blogs.msdn.microsoft.com/kcwalina/2004/10/24/api-design-myth-interface-as-contract/
http://martinfowler.com/bliki/RoleInterface.html
http://martinfowler.com/bliki/HeaderInterface.html

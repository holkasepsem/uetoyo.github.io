# Scala, SBT, Eclipse

## Instalace SBT

Nainstalujeme si (SBT (Scala Build Tool))[http://www.scala-sbt.org]
Pozor, Scala samotná se neistaluje, i když je to možné. Vše necháme na SBT, které stáhne požadovanou verzi Scaly k projektu.
Ze (stránek)[http://www.scala-sbt.org/download.html] SBT si stáhneme určenou pro naši platformu a spustíme instalaci.

Pokud máme naistalovaný SBT, který by měl být v cestě, pak stačí do konzole
zapsat příkaz `sbt`, měl bychom se dostat do interaktivního módu.

    $ sbt
    > 

Zkusme zapsat příkaz `help` a uvidíme co všechno nám SBT nabízí. Jeden z příkazů
je `exit`, který použijeme a ukončíme tak interaktivní režim.

    > exit

## Vytvoření adresářů projektu

Nyní si vytvoříme kostru projektu. SBT bohužel neumí vytvořit kostru projektu,
proto se to řeší jednoduchým skriptem, který za nás potřebné adresáře vytvoří.
SBT rozumí adresářové struktuře, jako dodržuje např. Maven popsanou 
(zde)[https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html].

Následující příkaz vytvoří adresáře z příkazové řádky.

    $ mkdir -p scala-starter/src/{main,test}/scala/scala-starter

Struktura adresářů by měla vypadat takto:

    scala-starter
        src
            main
                scala
                    scala-starter
            test
                scala
                    scala-starter

Pokud plánujeme psát některé části v jazyku Java, pak můžeme přidat do `main` a `test` podadresáře
`java`.

## Vytvoření `build.sbt` souboru.

V kořenovém adresáři si vyvtoříme soubor `build.sbt` do kterého zapíšeme 
minimum pro to, aby byl SBT shcopen náš projekt sestavit.

    name := "scala-starter"

    scalaVersion := "2.12.0" 

## Skript pro generování projektu

https://gist.github.com/uetoyo/c0a1c31be5146516f85b11b123a14b82

## Zdroje

http://www.scala-sbt.org/index.html
http://www.scala-lang.org/index.html
https://maven.apache.org
http://alvinalexander.com/scala/how-to-create-sbt-project-directory-structure-scala
http://alvinalexander.com/sbtmkdirs
https://gist.github.com/alvinj/3194379
https://github.com/alvinj/BasicScalaSbtProjectWithScalatest
https://gist.github.com/djspiewak/cb72c41ac335a3a9b28b3307be04aa43

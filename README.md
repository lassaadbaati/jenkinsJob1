# jenkinsJob1

scrit à mettre dans le job 

# 3 jobs :
	- 1-build
	- 1-run
	- 1-test


# BUILD 
java (normalement avec git) et on compile


```
mkdir -p /tmp/lassaad/
rm -rf /tmp/lassaad/*
echo '
public class Main {
    public static void main(String[] args) {
        System.out.println("Hi De la part de l uit !");
    }
}
'  >/tmp/lassaad/Main.java
javac /tmp/lassaad/Main.java
```

-------------------------------------------------------

# RUN 

* lancement du java avec écriture dans un fichier du résultat

* créer une dépendance avec le build

```
cd /tmp/lassaad/
java Main >test.file
```
-------------------------------------------------------

# TEST 


* dépendant du déclenchement du RUN
* un principe
* on affiche le contenu du fichier test.file (on pourrait faire des tests dessus)

```
cd /tmp/lassaad/
echo "###### contenu du test.file ######"
cat test.file
```

------------------------------------------

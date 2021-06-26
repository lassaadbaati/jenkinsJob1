# jenkinsJob1
jenkinsJob1
scrit à mettre dans le job 
* retenir le principe pas le fond

* exemple : "Hello World"

* 3 jobs :
		- 1-build
		- 1-run
		- 1-test

--------------------------------------------------------

-> BUILD <-

* java (normalement avec git) et on compile


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

-> RUN <-

* lancement du java avec écriture dans un fichier du résultat

* attention dépendance avec le build

```
cd /tmp/lassaad/
java Main >test.file
```
-------------------------------------------------------

-> TEST <-


* dépendant du déclenchement du RUN

* un principe

* on affiche le contenu du fichier test.file (on pourrait faire des tests dessus)


```
cd /tmp/lassaad/
echo "###### contenu du test.file ######"
cat test.file
```

------------------------------------------------
* modèle : https://jenkins.io/doc/book/pipeline/

```
pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
                // 
            }
        }
        stage('Test') { 
            steps {
                // 
            }
        }
        stage('Deploy') { 
            steps {
                // 
            }
        }
    }
}
```
--------------------------
# pipeline
```
pipeline {
    agent any 
    stages {
        stage('clone') { 
            steps {
                sh "rm -rf *"
                sh "git clone https://github.com/lassaadbaati/jenkins-helloworld"
            }
        }
        stage('build') { 
            steps {
                sh "cd jenkins-helloworld/ && javac Main.java"
            }
        }
        stage('run') { 
            steps {
                sh "cd jenkins-helloworld/ && java Main"
            }
        }
    }
}
```

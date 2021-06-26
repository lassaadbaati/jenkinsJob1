# modèle de pipeline
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
# pipeline 1
// code java depuis githb avec des commandes shell

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

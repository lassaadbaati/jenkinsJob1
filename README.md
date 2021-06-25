# jenkinsJob1
jenkinsJob1
scrit à mettre dans le job 
job build
------------------------------------
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
---------------------------------
job run

--------------------------
pipeline
------------------------
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
---------------------------------

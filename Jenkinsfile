pipeline {

    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('clean') {
            steps {
                sh "mvn clean -f hello-world-sample-project-lolc"
            }
        }

        stage('install') {
            steps {
                sh "mvn install -DskipTests -f hello-world-sample-project-lolc"
            }
        }

        stage('package') {
            steps {
                sh "mvn package -DskipTests"
            }
        }

        // stage('Build Docker Image with Kaniko') {
        //     steps {
        //         container('kaniko') {
        //             script {

        //                 // Run Kaniko Build Command
        //                 sh "pwd"
        //                 sh "ls -a"
        //                 sh "/kaniko/executor --dockerfile `pwd`/Dockerfile --context `pwd` --destination=us-central1-docker.pkg.dev/cloudev-tech-trail/cloudev-practical/hello-world:v1 --verbosity=debug" 
        //             }
        //         }
        //     }
        // }

    }
}

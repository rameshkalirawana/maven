pipeline {
    agent any

    
        stage ('Package Stage') {
            steps {
                withMaven(maven : 'localMaven') {
                    sh 'mvn clean package'
                }
            }
        }
    }


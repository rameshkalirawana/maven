pipeline {
    agent any

    

        stage ('package Stage') {
            steps {
                withMaven(maven : 'localMaven') {
                    sh 'mvn clean package'
                }
            }
        }
    }
}

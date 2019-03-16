pipeline {
    agent any

     stages {
        
         stage ('Validate Stage'){
         
             steps {
                 withMaven(maven : 'Local_Maven'){
                     sh 'mvn clean validate'
                }
            }
         }
         
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'Local_Maven') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'Local_Maven') {
                    sh 'mvn test'
                }
            }
        }
        
        stage ('Package Stage') {

            steps {
                withMaven(maven : 'Local_Maven') {
                    sh 'mvn clean package'
                }
            }
        }
        
       stage ('Verify Stage') {

            steps {
                withMaven(maven : 'Local_Maven') {
                    sh 'mvn verify'
                }
            }
        }
        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'Local_Maven') {
                    sh 'mvn install'
                }
            }
        }
    }
}

pipeline {

   agent any

   parameters {
               string(name:'COMPONENT', defaultValue: '', description: 'enter which component')
               string(name:'APP_VERSION', defaultValue: '', description: 'enter APPLICATION version to deploy ')
   }
   stages{
      stage('Get values from files') {
        steps {
          dir ('APP'){
            git branch: 'main', url: 'https://github.com/pcs1999/${COMPONENT}.git'
          }
        }
      }

      stage ('Helm deploy')
        steps {
         sh ' find frontend'
        }

   }
}
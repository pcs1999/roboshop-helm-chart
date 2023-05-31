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

          dir('HELM') {
               git branch: 'main', url: 'https://github.com/pcs1999/roboshop-helm-chart.git'
          }
        }
      }

      stage('Helm deploy') {
        steps {
         sh 'helm upgrade -i ${COMPONENT} ./HELM -f APP/values.yaml --set-string image.tag="${APP_VERSION}"'
        }
      }
   }

   post {
   always {
     cleanws()
   }
   }
}
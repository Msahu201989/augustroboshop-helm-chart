pipeline{
 agent any

    parameters {
      string(name: 'component', defaultValue: '', description: 'Component Name')
      string(name: 'appVersion', defaultValue: '', description: 'Component appVersion')
    }

  satges {

    stage('checkout Application Code') {
      steps {
        dir('APP') {
          git branch: 'main', url: 'https://github.com/Msahu201989/${COMPONENET}'



        }
    }
     stage('Helm Deploy') {
          steps {
            sh '''
              helm install ${component} . -f APP/helm/prod.yml
            '''
          }
        }
     }
   }
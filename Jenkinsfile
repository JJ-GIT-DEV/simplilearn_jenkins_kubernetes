
pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/justmeandopensource/playjenkins.git', branch:'test-deploy-stage'
      }
    }

    stage('Deploy in kube wordpress') {
      steps {
        script {
          kubernetesDeploy(configs: "kubedeploy.yml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}


pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/JJ-GIT-DEV/simplilearn_jenkins_kubernetes.git', branch:'main'
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

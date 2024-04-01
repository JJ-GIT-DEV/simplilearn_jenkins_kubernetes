
pipeline {
  agent {
    kubernetes {
      label 'kubernetes'
    }
  }

  stages {
    stage('Checkout Source') {
      steps {
        git url:'https://github.com/JJ-GIT-DEV/simplilearn_jenkins_kubernetes.git', branch:'main'
      }
    }

    stage('Deploy in kube wordpress') {
      steps {
        script {
          kubernetesDeploy(configs: "kubedeploy.yml", kubeconfigId: "jenkins-local")
          //withKubeConfig ([credentialsId: 'local_cluster_k8s'])
          //{
          //  sh 'kubectl create -f $WORKSPACE/kubedeploy.yml'
          //}
        }
      }
    }
  }
}
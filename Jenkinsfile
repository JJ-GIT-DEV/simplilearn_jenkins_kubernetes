
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
    stage('Deploy to k8s wordpress'){
      steps{
        script{
//          kubeconfig(credentialsId: 'jenkins-local', serverUrl: 'https://172.31.21.200:6443') {
//              sh 'kubectl get nodes'
//          } // error cannot run programm kubectl no such file or directory
          withKubeConfig ([credentialsId: 'jenkins-local'])
          {
            sh 'kubectl create -f $WORKSPACE/kubedeploy.yml'
          }
        }
      }
    }
          //kubernetesDeploy(configs: "kubedeploy.yml", kubeconfigId: "jenkins-local")

  }
}
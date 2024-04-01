
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
          kubeconfig(credentialsId: 'jenkins-local', serverUrl: 'https://172.31.21.200:6443') {
              sh 'kubectl get nodes'
          }
        }
      }
    }
          //kubernetesDeploy(configs: "kubedeploy.yml", kubeconfigId: "jenkins-local")
          //withKubeConfig ([credentialsId: 'local_cluster_k8s'])
          //{
          //  sh 'kubectl create -f $WORKSPACE/kubedeploy.yml'
          //}
  }
}
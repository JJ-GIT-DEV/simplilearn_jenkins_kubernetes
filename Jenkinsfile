
pipeline {

  agent {

    kubernetes {

      label 'local_kubernetes'

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
          // kubernetesDeploy(configs: "kubedeploy.yml", kubeconfigId: "mykubeconfig")
          withKubeConfig ([credentialsId: 'local_cluster_k8s'])
          {
            sh 'kubectl create -f $WORKSPACE/kubedeploy.yml'
          }
        }
      }
    }
  }

}

    stage('Deploying React.js container to Kubernetes') {
      steps {
        script {
          kubernetesDeploy(configs: "deployment.yaml", 
                                         "service.yaml")
        }
      }
    }
pipeline {
    agent {
      label 'linux'
    }
    stages {
//        stage('checkout DIR') {
//            steps {
//               git branch: 'main', credentialsId: '10410357-13d3-4cf2-a45d-c65629928354', url: 'git@github.com:pavelmm/roles-vector.git'
//                
//        }
//   }
        stage('Molecule install') {
            steps{
                sh 'pip install molecule==3.4.0'
                sh 'pip install "ansible-lint<6.0.0"'
                sh 'pip install molecule_docker'
            }
        }
        stage('Molecule test'){
            steps{
                sh 'molecule test -s centos7'
                cleanWs()
            }
        }
    }
}
pipeline {
    agent any
    parameters {
  string defaultValue: 'Kirill Botalov', name: 'MY_STRING'
}
    stages {
        stage('Build and Run') {
            steps {
                sh 'apt install -y python3-pip'
                sh 'pip install -r requirements.txt'
                sh 'python3 hello.py -n "${MY_STRING}" > result.txt'
            }
        }
        stage('RESULT') {
            steps {
                archiveArtifacts artifacts: 'result.txt'
            }
        }
    }
}

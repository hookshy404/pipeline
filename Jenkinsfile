pipeline {
    agent any

    stages {
        stage('CHECKOUT INPUT FILE') {
            steps {
                git url: 'https://github.com/hookshy404/input.git', branch: 'master'
                sh' echo "input data:"'
                sh' cat data.txt'
                sh' echo "my first pipeline"'
            }
        }
    }
}

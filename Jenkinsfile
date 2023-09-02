pipeline {
    agent any
    parameters {
        // deploy everything (but idempotency is managed)
        string(name: 'DEPLOY', defaultValue: "gpa")
    }
    stages {
        stage('CHECKOUT INPUT FILE') {
            steps {
                git url: 'https://github.com/hookshy404/input.git', branch: 'master'
                sh' echo "input data:"'
                sh' cat data.txt'
                sh' echo "my first pipeline"'
                sh' echo "${DEPLOY}"'
            }
        }
    }
}

pipeline {
    agent any
    parameters {
        // deploy everything (but idempotency is managed)
        string(name: 'DEPLOY', defaultValue: "gpa")
    }
    environment {
      SMAVSUP_SP_HOST = "smavsupgw"
    }
    stage ('Set environment') {
        steps {
            script 
                  // following values are set in setEnv script and if not defined as parameters are set to unwanted default values
                  env.SMAVSUP_SP_HOST = "ID_${DEPLOY}"
    }
    stages {
        stage('CHECKOUT INPUT FILE') {
            steps {
                git url: 'https://github.com/hookshy404/input.git', branch: 'master'
                sh' echo "input data:"'
                sh' cat data.txt'
                sh' echo "my first pipeline"'
                sh' echo "${DEPLOY}"'
                sh' echo "${env.SMAVSUP_SP_HOST}"'
            }
        }
    }
}

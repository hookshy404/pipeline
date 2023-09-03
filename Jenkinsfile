pipeline {
    agent any
    parameters {
        // deploy everything (but idempotency is managed)
        string(name: 'DEPLOY', defaultValue: "gpa")
    }
    environment {
      SMAVSUP_SP_HOST = "smavsupgw"
        FAS_IOC_SWC = ""
        IOC_INSTANCE_PREFIX = "smavsup"
    }
    //stage ('Set environment') {
        //steps { // following values are set in setEnv script and if not defined as parameters are set to unwanted default values
                 // env.SMAVSUP_SP_HOST = "ID_${DEPLOY}"
        //}}
    stages {
        stage('CHECKOUT INPUT FILE') {
            steps {
                git url: 'https://github.com/hookshy404/input.git', branch: 'master'
                sh' echo "input data:"'
                sh' cat data.txt'
                sh' echo "my first pipeline"'
                sh' echo "${DEPLOY}"'
                sh' echo ${SMAVSUP_SP_HOST}'
                sh' echo \${SMAVSUP_SP_HOST}'
                //sh' printenv'
                
            }
        }
        stage('with env'){
            steps {
                withEnv([ "FAS_IOC_SWC= MyOpcUa" ]) {
                        sh( label: 'test', script:
                           """
                           echo "${FAS_IOC_SWC}"
                           """
                           )
                }//with env
                
            }
        }
    }
}


pipeline {
    // 指定运行节点
    // agent any
    agent {
        label 'ansible-lzll-hk'
    }
    // 打开运行时间戳
    options {
        timestamps()
    }
    environment {
        codeurl = 'xxxx'
    }
    stages {
        stage ('checkout code') {
            steps {
                checkout([$class: 'GitSCM', 
                branches: [[name: '*/dev']], 
                doGenerateSubmoduleConfigurations: false, 
                extensions: [], 
                submoduleCfg: [], 
                userRemoteConfigs: [[credentialsId: 'cibuild-sshkey', 
                url: "${codeurl}"]]
                ])               
            } 
        }  
    }
} 
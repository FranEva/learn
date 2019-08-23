
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
        approvalMap = ''
    }    
    stages {
        // stage ('pre deploy') {
        //     steps {
        //         script {
        //             approvalMap = input (
        //                 message: "准备发布到哪个环境？",
        //                 ok: "确定",
        //                 parameters: [
        //                     choice(name: 'ENV', choices: ['dev', 'test', 'prod'], description: '发布到什么环境？')
        //                     string(name: 'myparam', defaultValue: '', description: '')
        //                 ],
        //                 submitter: "admin,admin2,releaseGroup",
        //                 submitterParameter: "APPROVER"
        //             )
        //         }
        //     }
        // }
        // stage ('deploy') {
        //     steps {
        //         echo "操作者是 ${approvalMap['APPROVER']}"
        //         echo "发布到什么环境？ ${approvalMap['ENV']}"
        //         echo "自定义参数： ${approvalMap['myparam']}"
        //     }
        // }
        // stage('Example') {
        //     input {
        //         message "Should we continue?"
        //         ok "Yes, we should."
        //         submitter "alice,bob"
        //         parameters {
        //             string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        //         }
        //     }
        //     steps {
        //         echo "Hello, ${PERSON}, nice to meet you."
        //     }
        // }
        stage ('deploy') {
            options {
                // timeout(time: 10, unit: 'HOURS')
                timeout(time: 1, unit: 'MINUTES')
                // timeout(time: 1, unit: 'SECONDS')
            }
            steps {
                input message: "继续或者停止？"
            }
        }
    }
} 
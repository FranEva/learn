// 定义变量的方法
def vars1 = 'vars1'

// 自定义函数设置版本
def getDateTime() {
    sh(returnStdout: true, script: 'date +%Y%m%d').trim()
}

pipeline {
    // 指定运行节点
    agent any
    // agent {
    //     label 'any'
    // }
    // 打开运行时间戳
    options {
        timestamps()
    }
    environment {
        vars2 = 'vars2'
    }
    stages {
        stage ('打印变量的值') {
            steps {
                script {
                   sh "echo ${vars1}"
                   sh "echo ${vars2}"
                   // 以下三个没有区别，都是打印当前的构建数
                   sh "echo ${BUILD_NUMBER}"
                   sh "echo ${env.BUILD_NUMBER}"
                   echo "${BUILD_NUMBER}"
                   // 打印名称，第一个是全路径/var/jenkins_home/workspace/1/test，第二个是文件名本身，
                   sh "echo ${JOB_NAME}" // 1/test
                   sh "echo ${JOB_BASE_NAME}" // test
                }
            }
        }
        stage("自定义变量的获取"){
            steps {
                echo "没有在script里面执行"
                // script声明Pipeline中的步骤不是必须的
                script {
                    env.PIPELINE_VERSION = "${getDateTime()}-${env.BUILD_NUMBER}"
                    echo "没有sh的 Set Pipeline Version: ${env.PIPELINE_VERSION}"
                    // 输出 没有sh的 Set Pipeline Version: 20190813-27
                    sh "echo 有sh的 Set Pipeline Version: ${env.PIPELINE_VERSION}"
                    // 输出 有sh的 Set Pipeline Version: 20190813-27
                }
            }
        }
    }
} 
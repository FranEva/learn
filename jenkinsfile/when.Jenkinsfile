
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
    parameters {
        // 输入型，和txt的区别就是只能一行
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        // 输入型 和string的区别就是可以多行
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        // 勾选项 二次确认这种
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        // 选择项 选择构建
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        // 密码项
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')

    }
    stages {
        stage ('输出默认值') {
            steps {
                echo "${PERSON}"
                echo "${BIOGRAPHY}"
                echo "${TOGGLE}"
                echo "${CHOICE}"
                echo "${PASSWORD}" // 这里是输出明文密码
            }
        }
        stage ('输入型') {
            when { expression { return params.PERSON == 'Mr Jenkins'} }           
            steps {
                echo "The PERSON is ${PERSON}"
            }
        }
        stage ('选择型1') {
            when { expression { return params.CHOICE == 'One'} }           
            steps {
                echo "you CHOICE is ${CHOICE}"
            }
        }
        stage ('选择型2') {
            when { expression { return params.CHOICE == 'Two'} }           
            steps {
                echo "you CHOICE is ${CHOICE}"
            }
        }
        stage ('与逻辑') {
            when { expression { return params.CHOICE == 'Two' &&  params.PERSON == 'Mr Jenkins' } }           
            steps {
                echo "都同时成立！！"
            }
        }
        stage ('或逻辑') {
            when { expression { return params.CHOICE == 'Two' ||  params.PERSON == 'Mr Jenkins' } }           
            steps {
                echo "有一个同时成立！！"
            }
        }                
    }
} 
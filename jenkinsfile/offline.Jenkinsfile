def sposeofflinerun = 'E:\\spose_offline\\SposeDeploymentFile\\runAll.bat'

pipeline {
    // 指定运行节点
    // agent any
    agent    none 
    // 打开运行时间戳
    options {
        timestamps()
    }
    parameters {
        string(name: 'name', defaultValue: 'name', description: '')
        string(name: 'data', defaultValue: 'data', description: '')
    }    
    stages {
        stage ('Sequential') {
            stages {
                stage ('run In Parallel') {
                    parallel {
                        // stage('In Parallel 190') {
                        //     agent {   label 'sposeoffline-190' }
                        //     steps {
                        //         bat "${sposeofflinerun}"
                        //     }
                        // }
                        // stage('In Parallel 191') {
                        //     agent {   label 'sposeoffline-191' }
                        //     steps {
                        //         bat "${sposeofflinerun}"
                        //     }
                        // }                        
                        // stage('In Parallel 192') {
                        //     agent {   label 'sposeoffline-192' }
                        //     steps {
                        //         bat "${sposeofflinerun}"
                        //     }
                        // }
                        // stage('In Parallel 193') {
                        //     agent {   label 'sposeoffline-193' }
                        //     steps {
                        //         bat "${sposeofflinerun}"
                        //     }
                        // }                        
                        stage('In Parallel 194') {
                            agent {   label 'sposeoffline-194' }
                            steps {
                                bat "${sposeofflinerun}"
                            }
                        }
                    }
                }
                // stage ( 'run node 199') {
                //     agent {   label 'sposeoffline-199' }
                //     steps { 
                //         bat " E:\\Spose_offline_tool\\image_jekins\\compute_2d.exe  ${name} ${data} "
                //     }
                // }
            }
        }
    }
}
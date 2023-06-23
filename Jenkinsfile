pipeline{
    agent any
        environment{
            name = "test"
            url = "http://localhost:8080"
        }
        stages{
            stage('Build-1'){
                steps{
                    sh 'echo "hello worlds"'
                    sh '''
                    echo $name
                    echo $url
                    echo "first step"
                    sleep 5
                    '''
                }
                when{
                    environment name: 'name', value: 'test'
                }
            }

            stage('Build-2'){
                steps{
                    sh 'echo "hello worlds"'
                    sh '''
                    echo $name
                    echo $url
                    echo "first step"
                    sleep 10
                    '''
                }
                when{
                    environment name: 'name', value: 'production'
                }
            }
            stage('Build-3'){
                steps{
                    sh '''
                    echo Build3
                    sleep 5
                    '''
                }
                parallel{
                        stage('Paralel-1'){
                            steps{
                                sh '''
                                echo 'first paralel'
                                sleep 10
                                '''
                            }
                        }
                        stage('Paralel-2'){
                            steps{
                                sh '''
                                echo 'first paralel-2'
                                sleep 5
                                '''
                            }
                        }
                    }
                }
            }


        }
        post{
            success {
                sh '''
                echo "SUCCESSIONN"
                echo "post ${name}"
                '''
            }
        }

pipeline
        {
            tools
            {
                jdk 'myjava'
                maven 'mymaven'
            }
            agent none
            stages
            {
                 stage('Compile')
                    {
                        agent any
                        steps
                        {
                        sh 'mvn compile'
                        }
                    }
                    stage('Test')
                    {
                        agent any
                        steps
                        {
                        sh 'mvn test'
                        }
                    }
                    stage('Package')
                    {
                        agent {label 'linux_slave'}
                        steps
                        {
                        git 'https://github.com/Bhavyakotti/game-of-life.git'    
                        sh 'mvn package'
                        }
                    }
                
            }
        }

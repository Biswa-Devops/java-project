pipeline{
        agent any
        tools{
                maven 'maven3.9'
                stages{
                        stage("checkout code")
                        steps{
                                echo("checkout started")
                                git branch: 'master',url: https://github.com/Biswa-Devops/java-project.git
                                echo("checkout complete")
                stages{
                        stage("build code")
                        steps{
                                echo("build started")
                                sh 'mvn clean package'
                                echo('build complete')
                 stage{
                        stage("Deployment code")
                        steps{
                                echo("Deployment started")
                                deploy adapters: [tomcat9(credentialsId: 'tomcatcred',url: 'http://3.111.52.56:8080/')],contextPath: 'welcomeapp',war: '*/.war'
                                echo("Deployment complete")
                        }
                 }               
                        }

                }                
                        }
                }
        }
}
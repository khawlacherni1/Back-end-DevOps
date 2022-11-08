pipeline {
    agent any
    stages{
        stage('Git Checkout'){
            steps{
                git 'https://github.com/khawlacherni1/Back-end-DevOps.git'
            }
        }
        /*stage('UNIT Testing'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Integration testing'){
            steps{
                sh 'mvn verify -DskipUnitTests'
            }
        }
    }*/


    /*stage('Maven-clean'){
                steps{
                    script{
                        sh 'mvn clean'
                    }
                }
            }*/

    stage("Cleaning project") {
                steps {
                    sh "./mvnw clean"
                }
            }
    stage("Compiling project") {
                steps {
                    sh "./mvnw compile"
                }
            }

    /*stage('Maven-test'){
                steps{
                     script{
                        sh 'mvn test'
                            }
                        }
                    }
    stage('Compile-package'){
            steps{
                script{
                    sh 'mvn package'
                }
            }
        }*/
    }



    /*stages{
        stage('Compile-package'){
            steps{
                script{
                    sh 'mvn package'
                }
            }
        }
        stage('Sonarqube Analysis'){
            steps{
                script{
                    jacoco()
                    def mvnHome = tool name: 'maven', type: 'maven'
                    withSonarQubeEnv('sonar2'){
                        sh "${mvnHome}/bin/mvn verify sonar:sonar"
                    }
                }
            }
        }
        stage("Quality gate status check") {
            steps {
                script{
                sleep(60)
              timeout(time: 1, unit: 'MINUTES') {
                def qg = waitForQualityGate()
                if(qg.status != 'OK') {
                    slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '#jenkins-notifications', color: 'danger', message: 'Pipeline aborted: Sonarqube Analysis marked as failed', teamDomain: 'Legion14', tokenCredentialId: 'slack-channel'
                    error "Pipeline aborted due to quality gate failure: ${qg.status}"
                }
                }
              }
            }
          }
        stage('Email Notification'){
            steps{
                script{
                    mail bcc: '', body: '''Hi,
Welcome to jenkins email alerts.
Thanks,
Anas''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'anasbo7@hotmail.com'
                }
            }
        }
        stage('Slack Notification'){
            steps{
                script{
                    slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '#jenkins-notifications', color: 'good', message: 'Welcome to jenkins notifications channel, legionaries. Sent from Jenkins', teamDomain: 'Legion14', tokenCredentialId: 'slack-channel'
                }
            }
        }
        stage('Build And Deploy Docker Image'){
                    steps{
                        script{
                            echo "deploying the application"
                            withCredentials([usernamePassword(credentialsId:'dockerhub',usernameVariable:'USER',passwordVariable:'PWD')]) {
                                sh "echo $PWD | docker login -u $USER --password-stdin"
                                sh "docker build -t anasbenouaghrem/spring-app:1.0 ."
                                sh "docker push anasbenouaghrem/spring-app:1.0"

                        }
                    }
                }
            }
    }*/
}

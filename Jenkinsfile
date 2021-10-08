//pipeline {
//    agent none
////    agent {
////        node {
////            label 'WORKSTATION'
////        }
////    }
//
//    options { disableConcurrentBuilds() }
//
//    tools {
//        maven 'maven'
//    }
//
//    parameters {
//        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//
//        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
//
//        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
//
//        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
//
//        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
//    }
//
//    environment {
//        SAMPLE_URL = "google.com"
//        SLACK_TOKEN = credentials('slack')
//    }
//
//    stages {
//
//        stage('One') {
//            agent {
//                node {
//                    label 'NODEJS'
//                }
//            }
//            input {
//                message "Should we continue?"
//                ok "Yes, we should."
//                //submitter "alice,bob"
//                parameters {
//                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
//                }
//            }
//            steps {
//                sh 'echo Hello World'
//                sh 'echo ${SAMPLE_URL}'
//                sh 'echo ${SLACK_TOKEN}'
//            }
//        }
//
//        stage('Two') {
//            when {
//                environment name: 'SAMPLE_URL', value: 'yahoo'
//            }
//            agent {
//                node {
//                    label 'JAVA'
//                }
//            }
//            environment {
//                SAMPLE_URL = "yahoo.com"
//            }
//            steps {
//                sh 'echo Hello World'
//                sh 'echo ${SAMPLE_URL}'
//                sh 'mvn --version'
//            }
//        }
//
//    }
//
//
//    post {
//        success {
//            slackSend color: "good", message: "Message from Jenkins Pipeline"
//        }
//
//        failure {
//            slackSend color: "danger", message: "FAILURE"
//        }
//    }
//
//}


pipeline {
    agent any
    stages {
        stage('Seq1') {
            steps {
                sh 'echo Hello'
            }
        }
        stage('Par1') {
            parallel {
                stage('p1') {
                    steps {
                        sh 'sleep 10'
                    }
                }
                stage('p2') {
                    steps {
                        sh 'sleep 100'
                    }
                }
                stage('p3') {
                    steps {
                        sh 'sleep 10'
                    }
                }
            }
        }
        stage('Par2') {
            parallel {
                stage('p1') {
                    steps {
                        sh 'sleep 10'
                    }
                }
                stage('p2') {
                    steps {
                        sh 'sleep 100'
                    }
                }
                stage('p3') {
                    steps {
                        sh 'sleep 10'
                    }
                }
            }
        }
        stage('Seq2') {
            steps {
                sh 'echo Hello'
            }
        }
    }
}
#!/usr/bin/env groovy

def label = "ragazzid-${UUID.randomUUID().toString()}"
def home = "/home/jenkins"
def workspace = "${home}/workspace/build-jenkins-operator"
def workdir = "${workspace}/src/github.com/jenkinsci/kubernetes-operator/"

podTemplate(label: label,
        containers: [
                containerTemplate(name: 'alpine', image: 'alpine:3.11', ttyEnabled: true, command: 'cat'),
        ],
        ) {
    node(label) {
        stage('Run shell') {
            container('alpine') {
                sh 'echo "hello world"'
            }
        }
		stage('Dormir por 10 min') {
            container('alpine') {
                sh 'sleep 300'
            }
        }
    }
}


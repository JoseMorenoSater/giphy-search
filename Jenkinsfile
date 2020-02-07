pipeline {
    agent {
        docker {
            image 'node:8'
            args '-p 3000:3000'
        }
    }
    environment {
        CI = 'true'
    }
    stages { 
        stage('Build'){
            steps {
                sh 'npm install'
            }
        }
        stage('Test'){
            steps {
                sh 'npm test'
            }
        }
        stage('Deploy'){
            steps {
                sh 'curl -X POST -H "Authorization:Bearer eyJraWQiOiIxIiwiYWxnIjoiSFMyNTYifQ.eyJpc3MiOiJBcHBEeW5hbWljcyIZVkzR1ZwMzl4QlRTUHlGU3ciLCJzdWIiOiJ0ZXN0IiwiaWRUeXBlIjoiQVBJX0NMSUVOVCIsImlkIjoiN2Y1YTkwNzYtN2FlOS00ZDU1LWE3N2UtN2I2ODE3MjA0ZDJlIiwiYWNjdElkIjoiZjYwYmJmMjktZjg5Ni00YzZiLTgxODMtZjhkZDdhOWJkOTc2IiwiYWNjdE5hbWUiOiJhZGEyMDE5MTIyNzA2MzQzMjUiLCJ0ZW5hbnROYW1lIjoiIiwiaWF0IjoxNTgxMDMzNTU3LCJuYmYiOjE1ODEwMzM0MzcsImV4cCI6MTU4MTExOTk1NywidG9rZW5UeXBlIjoiQUNDRVNTIn0.c9cTa0TdVR5McrJumjMCSTJ0DrWKyuQtErgkAKinFDc" 'https://ada201912270634325.saas.appdynamics.com/controller/rest/applications/5701/events?severity=INFO&summary=Release_$BUILD_ID&eventtype=CUSTOM&customeventtype=Deployment''
            }
        }
    }
}

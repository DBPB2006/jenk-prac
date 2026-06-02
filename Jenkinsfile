// pipeline{
//     agent any
//     stages{
//         stage("checkout"){
//             steps{
//                 git branch: 'main', url: "https://github.com/DBPB2006/jenk-prac.git"
//             }
//         }
//         stage("build"){
//             steps{
//                 sh "docker build -t jenkins:v1 ."
//             }
//         }
//         stage("run"){
//             steps{
//                 sh "docker run -d -p 8900:80 --name jenkins1 jenkins:v1"
//             }
//         }
//     }
//     post{
//     success{
//         echo "deployed successfully"
//     }
//     failure{
//         echo "deployment failed"
//     }
// }
// }
pipeline {
    agent any

    stages {
        stage('init') {
            steps {
                sh '/opt/homebrew/bin/terraform init'
            }
        }

        stage('plan') {
            steps {
                sh '/opt/homebrew/bin/terraform plan'
            }
        }

        stage('apply') {
            steps {
                sh '/opt/homebrew/bin/terraform apply -auto-approve'
            }
        }
    }
}
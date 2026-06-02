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
pipeline{
    agent any
    stages{
        stage("stage 1"){
            steps{
                sh """docker build -t jen:v1 ."""
            }
        }
        stage("stage 2"){
            steps{
                sh """docker run -d -p 8990:80 jen:v1"""
            }
        }
        stage("stage 3"){
            steps{
                sh """docker ps"""
            }
    }
        post{
            success{
                echo "deployed successfully"
            }
            failure{
                echo "deployment failed"
            }
        }
}
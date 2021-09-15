pipeline{
    agent any
    stages{

        stage("install"){
        steps{
            sh("composer install")
            sh("npm install")
            sh("npm run dev")
        }
        }
        stage("build"){
            steps{
                sh("./vendor/bin/sail up -d")
            }
        }

        stage("test"){
            steps{
                sh("./vendor/bin/sail test")
            }
        }

        stage("down"){
            steps{
                sh("./vendor/bin/sail down")
            }
        }
    }
}
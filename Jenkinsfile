pipeline{
    agent any
    triggers {
        pollSCM('* * * * *')
}
      stages{
        stage('vcs') {
            steps {
                git url: 'https://github.com/shaiksohail11/StudentCoursesRestAPI.git'
                    branch: 'develop'
            }
        }

        stage('build docker image') {
            steps{
                sh "docker image build -t shaik1128/studentcourse:1.1"
            }
        }

        stage('push to registry') {
            steps {
                sh "docker push shaik1128/studentcourse:1.1"
            }
        }

    
      }
}
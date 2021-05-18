pipeline{

    agent any

    stages {

        stage('Maven Package') {
            steps {
                sh '''
                mvn package
            '''
            }
        }
        stage('prepare Artifacts') {
            steps {
                sh '''
                zip -r ../users.zip *
            '''
            }

        }
        stage('upload Artifacts') {
            steps {
                sh '''
           curl -f -v -u admin:admin --upload-file todo.zip http://172.31.11.104:8081/repository/users/users.zip
        '''
            }
        }
    }
}
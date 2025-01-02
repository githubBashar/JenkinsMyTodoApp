node {
    stage('Preperation') {
        git branch: 'main', url: 'https://github.com/githubBashar/JenkinsMyTodoApp.git'
        bat 'dir' // Überprüfen der Verzeichnisstruktur
    }
    stage('Build') {
        dir('my-first-rest-app') { // Wechsel in das Unterverzeichnis
            bat "mvn clean test"
        }
    }
    stage('Package') {
        dir('my-first-rest-app') {
            bat "mvn package"
        }
    }
    stage('Results') {
        dir('my-first-rest-app') {
            junit '**/target/surefire-reports/TEST-*.xml'
            archiveArtifacts artifacts: 'target/*.jar', allowEmptyArchive: true
        }
    }
}

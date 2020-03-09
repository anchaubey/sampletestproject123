node{
    stage('Checkout the code')
    {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'GIT', url: 'https://github.com/anchaubey/sampletestproject123.git']]])
    }
    stage('Run unit test cases')
    {
        if(isUnix()){
            sh 'mvn test'
        }
        else{
            bat 'mvn test'
        }
    }
    stage('Package the artifact')
    {
        'sh clean package'
    }
    stage('Create a package')
    {
        if(isUnix()){
            sh 'mvn clean package'
        }
        else{
            bat 'mvn clean package'
        }
    }
     stage('Package the artifact')
    {
        'sh clean package'
    }
    stage('Send notification')
    {
        mail bcc: '', body: '''Build done
Regards,
Ankit Chaubey''', cc: 'ankitchaubey091987@gmail.com', from: '', replyTo: '', subject: 'Build Stage', to: 'ankitchaubey091987@gmail.com'
    }
}

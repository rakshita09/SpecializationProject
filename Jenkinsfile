pipeline {
    agent any
    tools {
         maven 'maven3'
    }
    stages{
        stage('Build'){
            steps{
                  sh script: 'mvn clean package'
            }
        }
        stage('Upload Jar To Nexus'){
            steps{ 
               nexusArtifactUploader artifacts: [
                 [
                   artifactId: 'SpringBootRest-3',
                   classifier: '',
                   file: 'target/SpringBootRest-3-0.0.1-SNAPSHOT.jar',
                   type: 'jar'
                 ]
               ],
                 credentialsId: 'b9356e13-8638-4663-9136-6aa7105785b6',
                 groupId: 'com.th',
                 nexusUrl: '3.87.60.100:8081',
                 nexusVersion: 'nexus3',
                 protocol: 'http', 
                 repository: 'Main', 
                 version: '0.0.1-SNAPSHOT'
            }
        }
    }
 }

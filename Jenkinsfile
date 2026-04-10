pipeline {
  agent any

  parameters {
     string(name: "App_Version", description: "provide application version")
  }

  environment {
    DOCKERHUB_CREDENTIALS = credentials("dockerhub")
  }

  stages {

    stage("Checkout") {
      steps {
        checkout scmGit(branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/rashmiranjanDevOps/student-datastore-ci-cd.git']])
      }
    }

    stage("Maven Build") {
      steps {
        sh '''
          echo "-------- Building Application --------"
          mvn clean package
          echo "------- Application Built Successfully --------"
        '''
      }
    }

    stage("SonarQube Analysis") {
      environment {
        SONAR_TOKEN = credentials('sonar-token')
      }
      steps {
        withSonarQubeEnv('SonarQube') {
          sh '''
            echo "-------- Running SonarQube Analysis --------"
            mvn sonar:sonar \
            -Dsonar.projectKey=datastore \
            -Dsonar.projectName=datastore \
            -Dsonar.login=$SONAR_TOKEN
            echo "-------- SonarQube Analysis Completed --------"
          '''
        }
      }
    }

    stage("Maven Test") {
      steps {
        sh '''
          echo "-------- Executing Testcases --------"
          mvn test
          echo "-------- Testcases Execution Complete --------"
        '''
      }
    }

    stage("Artifact Store") {
      steps {
        sh '''
          echo "-------- Pushing Artifacts To S3 --------"
          aws s3 cp ./target/*.jar s3://datastore-artefact-store-jenkins1/
          echo "-------- Pushing Artifacts To S3 Completed --------"
        '''
      }
    }

    stage("Docker Image Build") {
      steps {
        sh '''
          echo "-------- Building Docker Image --------"
          docker build -t datastore:${App_Version} .
          echo "-------- Image Successfully Built --------"
        '''
      }
    }

    stage("Docker Image Scan") {
      steps {
        sh '''
          echo "-------- Scanning Docker Image --------"
          trivy image datastore:${App_Version}
          echo "-------- Scanning Docker Image Complete --------"
        '''
      }
    }

    stage("Docker Image Tag") {
      steps {
        sh '''
          echo "-------- Tagging Docker Image --------"
          docker tag datastore:${App_Version} rashmiranjandevops/datastore:${App_Version}
          echo "-------- Tagging Docker Image Completed --------"
        '''
      }
    }

    stage("Login & Push Docker Image") {
      steps {
        sh '''
          echo "-------- Logging To DockerHub --------"
          echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin

          echo "-------- Pushing Docker Image --------"
          docker push rashmiranjandevops/datastore:${App_Version}

          echo "-------- Docker Image Pushed Successfully --------"
        '''
      }
    }

    stage("Cleanup") {
      steps {
        sh '''
           echo "-------- Cleaning Up Jenkins Machine --------"
           docker image prune -a -f
           echo "-------- Clean Up Successful --------"
        '''
      }
    }

    stage("Deployment Acceptance") {
      steps {
        input 'Trigger Down Stream Job??'
      }
    }
  }
}

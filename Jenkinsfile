pipeline{
  agent any 
  environment{
    DOCKERHUB_CREDENTIALS=credentials('docker')
  }
  stages{
    stage('checkout code')
    git branch 'main',url:'https://github.com/Thiriveedisatya/Dockertask.git'
  }
}
stage('build docker image'){
  steps{
    bat'docker build -t satyaimage1' .
      }
}
stage('run tests'){
  steps{
    script{
      bat 'docker run -d --name cont1 -p 8081:80 satyaimage1'
    }
  }
}
stage('Deploy image')
{
  steps{
    bat 'echo 
    $DOCKERHUB_CREDENTIALS_PSW
    docker login -u
    $$DOCKERHUB_CREDENTIALS_USR
    --password-stdin'
  }
}
stage('push image'){
  steps{
    bat 'docker tag satyajenkins Thiriveedisatya/satyajenkinsrepo'
    bat 'docker push Thiriveedisatya/satyajenkinsrepo'
  }
}
}

}

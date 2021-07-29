pipeline {
  agent any
  stages {
    stage('download') {
      steps {
		sh 'echo $(pwd) > path'
		sh 'cd $path'
		sh 'touch demofile1.txt'
        sh "curl $URLNAME --output demofile1.txt"
      }
    }
    stage('upload') {
      steps {
        sh 'aws s3 cp file.txt s3://$BUCKETNAME/demofile1.txt' 
      }
    }
  }
}

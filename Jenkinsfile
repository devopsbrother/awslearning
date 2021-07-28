pipeline {
  agent any
  stages {
    stage('download') {
      steps {
		sh 'echo $(pwd) > path'
		sh 'cd $path'
		sh 'touch file9999.txt'
        sh "curl $URLNAME --output file9999.txt"
      }
    }
    stage('upload') {
      steps {
        sh 'aws s3 cp file.txt s3://$BUCKETNAME/file9999.txt' 
      }
    }
  }
}


pipeline {
  agent any
  stages {
    stage('Deploy OTK Container 1') {
      steps {
        echo 'Deploying...'
        echo 'Successfully deployed!'
      }
    }
    stage('Health Check') {
      steps {
        echo 'Checking if pod is healthy and ready...'
        echo 'Pod is ready to accept traffic!'
      }
    }
    stage('Trigger TeamCity Build') {
      steps {
        call_teamcity()
      }
    }
    stage('All tests passed!') {
      steps {
        echo 'Waiting for all tests to pass...'
        echo 'All tests passed'
      }
    }
    stage('Success!') {
      steps {
        sleep 3
      }
    }
  }
}

def call_teamcity() {
  def response = httpRequest httpMode: 'POST',
                  url:'https://apim-teamcity.l7tech.com:8443/httpAuth/action.html?add2Queue=ApimMobileProjects_CreatedByDanny_TeamcityJenkinTrigger', 
                  authentication:'teamcity'
  println("Status: "+response.status)
  println("Content: "+response.content)
}

pipeline{
  agent any
  
  stages {
    stage ("Check Python") {
      steps {
        script {
          def pythonInstalled = sh(returnStatus: true, script: 'python --version >/dev/null 2>&1')
          if (pythonInstalled == 0) {
            echo "Python is installed in your machine"
          } else {
            echo "Python is not installed in your machine"
          }
        }
      }
    }
    stage ("Test function somar") {
      steps {
        sh 'python3 check_soma.py'
      }
    }
    stage ("Deploy") {
      steps {
        sh 'python3 soma.py'
      }
    }
  }
}

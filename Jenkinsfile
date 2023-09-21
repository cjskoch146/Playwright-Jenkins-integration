pipeline {
  agent any
//   { 
//     docker { 
//       image 'mcr.microsoft.com/playwright:v1.38.0-jammy'
//     } 
//   }
  stages {
    stage('install playwright') {
      steps {
        sh '''
          npm i -D @playwright/test
          npx playwright install
        '''
      }
    }
    stage('help') {
      steps {
        sh 'npx playwright test --help'
      }
    }
    stage('test') {
      steps {
        // --list flag will give an overview of all the tests that are being run
        sh '''
          npx playwright test --list 
          npx playwright test
        '''
      }
    }
  }
}

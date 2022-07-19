pipeline {
    agent { label 'spot-instance' }
    
    environment {
        currentDate = sh(returnStdout: true, script: 'date +%Y-%m-%d').trim()
    }
        stage ('Run another Job'){
            steps {
                build job: "Release Helpers/(TEST) Schedule Release Job2",
                parameters: [
                    [$class: 'StringParameterValue', name: 'ReleaseDate', value: "${currentDate}"]
 
                ]
            }
        }
}
 
/*
pipeline {
    agent any
    stages {
        stage('Example') {
            input {
                message "Let's promote?"
                ok 'Release!'
                parameters {
                    extendedChoice defaultValue: 'blue,green,yellow,blue', description: '', descriptionPropertyValue: 'blue,green,yellow,blue', multiSelectDelimiter: ',', name: 'favColor', quoteValue: false, saveJSONParameterToFile: false, type: 'PT_MULTI_SELECT', value: 'blue,green,yellow,blue', visibleItemCount: 5
                }
            }
            steps {
                echo "Your favorite color is ${favColor}"
            }
        }
    }
}
*/
/*
pipeline {
  agent any
  parameters {
    choice(name: 'door_choice',
      choices: 'one\ntwo\nthree\nfour',
      description: 'What door do you choose?')
    booleanParam(name: 'CAN_DANCE',
      defaultValue: true,
      description: 'Checkbox parameter')
    string(name: 'sTrAnGePaRaM',
      defaultValue: 'Dance!',
      description: 'Do the funky chicken!')
  }
  stages {
    stage('Example') {
      steps {
        echo 'Hello World!'
        echo "Trying: ${params.door_choice}"
        echo "We can dance: ${params.CAN_DANCE}"
        echo "The DJ says: ${params.sTrAnGePaRaM}"
      }
    }
  }
}
*/

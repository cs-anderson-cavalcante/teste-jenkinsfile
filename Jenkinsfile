pipeline {
  agent any
  stages{
stage('CodePull'){
  steps{
    dir ('ios'){ //criar ou entrar no diretorio, se exister ele entra, se nao, ele cria
      checkout([$class: 'GitSCM',
                  branches: [[name: 'master']], //branch a ser usada
                  doGenerateSubmoduleConfigurations: false,
                  extensions:
                  [[
                      $class: 'CloneOption', //padrão do codigo
                      depth: 1,
                      noTags: false,
                      reference: '',
                      shallow: true
                  ]],
                  userRemoteConfigs:
                  [[
                    credentialsId: 'a5f973d2-a275-4dad-beaf-f8574b9c3e95',
                    url: 'https://github.com/cs-anderson-cavalcante/teste-jenkinsfile.git'
                  ]]
                ])
      }
    }
  }
 }
}

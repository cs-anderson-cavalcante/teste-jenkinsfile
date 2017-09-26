pipeline {
  agent any //Setar o jenkins que ele vai usar, se for rodar no padrão, deixar ANY, se for em algum SLAVE setar o slave para cada stage
  stages{
stage('CodePull'){ //nome do job a ser criado
  steps{
    dir ('android'){ //criar ou entrar no diretorio, se exister ele entra, se nao, ele cria

      checkout([$class: 'GitSCM',
                  branches: [[name: 'master']], //branch a ser usada
                  doGenerateSubmoduleConfigurations: false,
                  extensions:
                  [[
                      $class: 'CloneOption', //padrão do codigo
                      depth: 1, //quantidades de commit que o shallow buscara
                      noTags: false,
                      reference: '',
                      shallow: true //buscara pela quantidade de commit setada no depth
                  ]],
                  userRemoteConfigs:
                  [[
                    credentialsId: 'a5f973d2-a275-4dad-beaf-f8574b9c3e95', //ID da credential criada para o user no jenkins
                    url: 'https://github.com/cs-anderson-cavalcante/poynt' // repositorio que buscaremos o jenkins
                      depth: 1,
                      noTags: false,
                      reference: '',
                      shallow: true
                  ]],
                ])
      }
    }
  }
 }
}
//Sempre que clonar um projeto, setar no DIR qual a pasta que iremos clonar.

stage('Build'){
      agent any
      steps{
        dir('build-android'){
          sh '''
            source $HOME/.bash_profile

            # Compila o app
            ./gradlew clean
            ./gradlew assmbleDebug
          '''
        }
      }
    }

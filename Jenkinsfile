stage('CodePull'){
  agent none
  steps{
    dir ('ios'){
      checkout([$class: 'GitSCM',
                  branches: [[name: '${gitAppSourceBranch}']],
                  doGenerateSubmoduleConfigurations: false,
                  extensions:
                  [[
                      $class: 'CloneOption',
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

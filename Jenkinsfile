#!groovy
node {
  parallel (
    'checkout repo1' : {
      // first repository
      checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/ekorekin/repo1']]])
    },
    'checkout repo2' : {
    // second repository
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/ekorekin/repo2']]])
    }
  )
  stage 'first script'
  // run first script
  load 'subdirectory1/Jenkinsfile1'
  stage 'second script'
  // run second script
  load 'subdirectory2/Jenkinsfile2'
}

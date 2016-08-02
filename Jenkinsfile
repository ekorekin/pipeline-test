#!groovy
node {
    // first repository
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'subdirectory1']], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/ekorekin/repo1']]])
    // second repository
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'subdirectory2']], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/ekorekin/repo2']]])
    // run first script
    load 'subdirectory1/Jenkinsfile'
    // run second script
    load 'subdirectory2/Jenkinsfile'
}

#!groovy
node {
    stage 'checkout repo1'
    // first repository
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'subdirectory1']], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/ekorekin/repo1']]])
    stage 'checkout repo2'
    // second repository
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'RelativeTargetDirectory', relativeTargetDir: 'subdirectory2']], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/ekorekin/repo2']]])
    stage 'first script'
    // run first script
    load 'subdirectory1/Jenkinsfile'
    stage 'second script'
    // run second script
    load 'subdirectory2/Jenkinsfile'
}

node {
   echo 'Welcome to first pipeline job'
   stage('CodeCheckout'){
         echo 'checkout'
         checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '80e1efa8-beb0-4cda-a199-d0bedde6feab', url: 'https://github.com/kanakaraju043/SampleApplication.git']]])
   }
   stage('Dependencies Install'){
         echo 'Dependencies Install'
         sh label: '', script: '/usr/local/bin/pod install'
   }
   stage('CodeUnitTest'){
         echo 'CodeUnitTest'
         xcodeBuild appURL: '', assetPackManifestURL: '', buildDir: '', bundleID: '', bundleIDInfoPlistPath: '', cfBundleShortVersionStringValue: '', cfBundleVersionValue: '', cleanBeforeBuild: false, cleanResultBundlePath: false, configuration: 'Debug', displayImageURL: '', fullSizeImageURL: '',ipaName: '', ipaOutputDirectory: '',logfileOutputDirectory: '', resultBundlePath: '', sdk: '', symRoot: '', target: '', thinning: '', xcodeProjectFile: '', xcodeProjectPath: '', xcodeSchema: 'SampleApplication', xcodeWorkspaceFile: 'SampleApplication', xcodebuildArguments: 'test  -destination \'platform=iOS Simulator,name=iPhone 8 Plus,OS=12.4\''  
   }
   stage('CodeBuild'){
         echo 'CodeBuild'
            xcodeBuild appURL: '', assetPackManifestURL: '', buildDir: '', bundleID: '', bundleIDInfoPlistPath: '', cfBundleShortVersionStringValue: '', cfBundleVersionValue: '', cleanBeforeBuild: false, cleanResultBundlePath: false, configuration: 'Debug', displayImageURL: '', fullSizeImageURL: '',ipaName: '', ipaOutputDirectory: '',logfileOutputDirectory: '', resultBundlePath: '', sdk: '', symRoot: '', target: '', thinning: '', xcodeProjectFile: '', xcodeProjectPath: '', xcodeSchema: 'SampleApplication', xcodeWorkspaceFile: 'SampleApplication', xcodebuildArguments: 'build  -destination \'platform=iOS Simulator,name=iPhone 8 Plus,OS=12.4\''  
   }
   stage('CodeDeploy'){
         echo 'CodeDeploy'
   }
   stage('Test Results'){
         echo 'Test Results'
         junit testDataPublishers: [[$class: 'AttachmentPublisher']], testResults: 'test-reports/*.xml'
   }
   
   
}

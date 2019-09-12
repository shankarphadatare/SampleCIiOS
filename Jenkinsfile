// This Jenkinsfile is used to build, test, and generate code coverage for an iOS project
// If you want to use this Jenkinsfile with your own project you'll need to make some changes:
// 1. Change the following variables to match your project
def xcodeproj = 'SampleCIiOS/SampleCIiOS.xcodeproj' // Path to the xcodeproj
def xcarchive_name = "SampleCIiOS.xcarchive" // Name of the archive to build
def build_scheme = 'SampleCIiOS' // Scheme to build the app
def test_scheme = 'SampleCIiOS' // Scheme to build tests
def simulator_device = 'iPhone 7' // Name of the device type to use for tests
// 2. If you want to upload builds to a server, update the buildURL variable and uncomment the scp command under stage('Save')
// 3. If you want Slack notifications, return true in the functions below and set the Slack channel
def slackChannel = '#general'


node {
    stage('Build') {
            echo 'Hi, this is shankar'
         // Just build for the example project
                // We can't archive because there's no code signing set up
                // Set up a development team and code signing to archive an ipa
                //sh "xcrun xcodebuild -scheme '${build_scheme}' -destination 'name=iPhone 7' clean build | tee build/xcodebuild.log | xcpretty"
        
                //sh "xcodebuild -scheme '${build_scheme}' build"
                sh "xcodebuild -scheme '${build_scheme}' -project '${xcodeproj}' -destination 'name=iPhone 7' build"

                // Uncomment this when building a project with code signing set up
                /*sh "xcrun xcodebuild -scheme '${build_scheme}' archive -archivePath 'build/${xcarchive_name}' | tee build/xcodebuild.log | xcpretty"
                sh "xcrun xcodebuild -exportArchive -exportOptionsPlist exportOptions.plist -archivePath 'build/${xcarchive_name}' -exportPath build"
                dir('build') {
                    sh "zip -qr 'Jenkins-iOS-Example-${env.BUILD_NUMBER}.zip' '${xcarchive_name}'"
                    sh "mv 'Jenkins iOS Example.ipa' 'Jenkins iOS Example-${branchNameForURL}.ipa'"
                }*/
        
        }
}

pipeline {
    agent any

    stages {
        stage('Comment on PR') {
            steps {
                script {
                    pullRequest.comment('Mess with the best, die like the rest.')

                    def pluginList = new ArrayList(Jenkins.instance.pluginManager.plugins)

                    pluginList.sort { it.getShortName() }.each{
                    plugin -> 
                            println ("${plugin.getDisplayName()} (${plugin.getShortName()}): ${plugin.getVersion()} : ${plugin.hasUpdate() ? plugin.getUpdateInfo().version : 'No Update'}")
                    }
                }
            }
        }
    }
}
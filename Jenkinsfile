#!groovy
node {
    stage 'Abort build: Check for nobuild conventional commit':
        result = sh (script: "git log -1 ${GIT_COMMIT} | egrep 'nobuild:.*'", returnStatus: true)
        if (result == 0) {
            currentBuild.result = 'NOT_BUILT'
            error "'nobuild' spotted in git commit. Aborting."
        }
}

node('master') {
    stage("Fetch Source Code") {
        cleanWS()
        git ([url:'https://github.com/sushmagoudar/python_jenkins_pipeline',branch:'add-functions-and-tests'])
    }
    
    dir('.'){
        printMessage('Running Pipeline')
        stage("Testing") {
            bat 'python test_functions.py'
        }
        stage("Deployment") {
            if (env.BRANCH_NAME == 'master') {
                printMessage('Deploying the master branch')
            } else {
                printMessage("No deployment for branch [${env.BRANCH_NAME}]")
            }
        } 
        }
        printMessage('Pipeline Complete')
    
}

def printMessage(message) {
    echo "${message}"
}

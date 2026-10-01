pipeline {
    agent any

    // Poll GitHub every 5 minutes (H spreads the load); no webhook needed
    triggers {
        pollSCM('H/5 * * * *')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Stage 1: Build'
                echo 'Task: Compile and package the code into a deployable artifact.'
                echo 'Tool: Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests'
                echo 'Task: Run unit tests to verify code behaviour and integration tests to verify components work together.'
                echo 'Tools: JUnit (unit tests), Selenium (integration tests)'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis'
                echo 'Task: Analyse the code for quality, bugs, code smells and adherence to industry standards.'
                echo 'Tool: SonarQube'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan'
                echo 'Task: Scan the code and its dependencies to identify known vulnerabilities.'
                echo 'Tool: OWASP Dependency-Check'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging'
                echo 'Task: Deploy the application to a staging server for pre-production validation.'
                echo 'Tool: AWS CodeDeploy (target: AWS EC2 staging instance)'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging'
                echo 'Task: Run integration tests against the staging environment to confirm it behaves as expected in a production-like setting.'
                echo 'Tool: Selenium'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production'
                echo 'Task: Deploy the verified application to the production server.'
                echo 'Tool: AWS CodeDeploy (target: AWS EC2 production instance)'
            }
        }
    }
}

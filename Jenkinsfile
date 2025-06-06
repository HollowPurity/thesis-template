pipeline {
    agent {
        dockerContainer {
            image 'blang/latex:ctanfull'
        }
    }

    stages {
        stage('Build PDF') {
            steps {
                dir('latex/tex') {
                    sh 'pdflatex thesis.tex'
                }
            }
        }

        stage('Archive PDF') {
            steps {
                archiveArtifacts artifacts: 'latex/tex/thesis.pdf', fingerprint: true
            }
        }
    }
}

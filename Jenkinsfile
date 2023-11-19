pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', changelog: false, credentialsId: 'Github-ssh', url: 'git@github.com:IronBlyzer/FlatMdSite.git'
            }
        }

        stage('Build') {
            parallel {
                stage('Generate Site') {
                    steps {
                        script {
                            echo 'En cours de construction'
                            // Add your site generation commands here
                        }
                    }
                }
                stage('Generate Docx') {
                    steps {
                        script {
                            echo 'Le fichier docs est entrain de se generer'
                            // Add your docx generation commands here
                        }
                    }
                }
            }
        }

        stage('Archive') {
            steps {
                script {
                    archiveArtifacts artifacts: '**/*', allowEmptyArchive: true
                }
            }
        }
    }

    post {
        success {
            echo 'Le pipeline a réussi, donc les artefacts ont été archivés.'
        }
        always {
            echo 'Le pipeline a été exécuté avec succès.'
        }
    }
}

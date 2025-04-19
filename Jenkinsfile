pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo 'Siemano z GitHuba!'
                echo 'ffasmpfoaajniefasfa'
                echo ' S222Iemano kolano co 22tam'
            }
        }
        stage('Watch Demo') {
            steps {
                script {
                    def seconds = 0
                    echo '⏳ Watch start – tracking long build step...'

                    // uruchamiamy w tle
                    def pid = sh(script: '''
        (
          while true; do
            echo "[watch] Build running for $(date +%T)"
            sleep 1
          done
        ) &
        echo $!
      ''', returnStdout: true).trim()

                    // tu udajemy, że coś długo się robi (np. kompilacja/testy)
                    try {
                        sh 'sleep 10' // <-- tutaj wrzuć swój długi krok
      } finally {
                        // ubijamy watcha
                        sh "kill ${pid}"
                        echo '✅ Watch finished – step done!'
                    }
                }
            }
        }
    }
}

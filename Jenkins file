pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''
                echo "Creating a new .cpp file"
                echo '#include <iostream>\\nusing namespace std;\\nint main() { cout << "Hello, Jenkins!"; return 0; }' > PES2UG22CS244-1.cpp
                
                echo "Compiling the .cpp file"
                g++ PES2UG22CS244-1.cpp -o PES2UG22CS244-1
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                echo "Running the compiled program"
                ./PES2UG22CS244-1
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                echo "Pushing to GitHub"
                '''
            }
        }
    }

    post {
        failure {
            echo "Pipeline failed"
        }
    }
}

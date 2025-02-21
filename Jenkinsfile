pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Running Pytest'

                # Initialize Conda
                source /home/nikitac/miniconda3/etc/profile.d/conda.sh

                # Activate the correct Conda environment
                conda activate mlip

                # Run pytest
                /home/nikitac/miniconda3/envs/mlip/bin/python -m pytest

                echo 'All tests passed successfully!'
                '''

            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
pipeline
{
    agent 
        { 
           label 'ubuntu'
        }
    stages
    {
        stage('clone')
        {
            steps
            {
               git credentialsId: 'ubuntu', 
                   url: 'https://github.com/tarunkumarpendem/python-sample-vscode-flask-tutorial.git',
                   branch: 'python'
            }
        }
        stage('shell_script')
        {
            steps
            {
                sh """python3 -m pip install --upgrade pip setuptools wheel,
                      pip install -r requirements.txt,
                      pip install pytest pytest-azurepipelines,
                      pip install pytest-cov,
                      pytest test_test1.py"""
            }
        }
    }
}

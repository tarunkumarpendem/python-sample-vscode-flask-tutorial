pipeline
{
    agent 
        { 
           label 'ubuntu-spc'
        }
    stages
    {
        stage('clone')
        {
            steps
            {
               git credentialsId: 'Ubuntu-Node', 
                   url: 'https://github.com/tarunkumarpendem/python-sample-vscode-flask-tutorial.git',
                   branch: 'master'
            }
        }
        stage('shell_script')
        {
            steps
            {
                sh """python3 -m pip install --upgrade pip setuptools wheel
                      pip install -r requirements.txt
                      pip install pytest pytest-azurepipelines
                      pip install pytest-cov
                      export PATH='/home/ubuntu/.local/bin:$PATH'
                      pytest test_test1.py"""
            }
        }
    }
}
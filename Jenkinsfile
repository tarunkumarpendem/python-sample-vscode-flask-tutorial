pipeline
{
    agent 
        { 
           label 'ubuntu'
        }
    parameters
    {
        choice(name: 'Branch_to_Build', choices: ['master', 'python'], description: 'choose the branch')
    }
    triggers 
    { 
        pollSCM('* * * * *') 
        
    }
    stages
    {
        stage('clone')
        {
            steps
            {
               git url: 'https://github.com/tarunkumarpendem/python-sample-vscode-flask-tutorial.git',
                   branch: "${params.Branch_to_Build}"
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
                      pytest test_test1.py"""
            }
        }
    }
}

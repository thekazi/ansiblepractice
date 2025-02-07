pipeline {
    agent any
    parameters {
        choice(name: 'ANSIBLE_PLAYBOOK', choices: 'setup_webserver.yml\ncreate_users.yml\nsetup_mysql.yml\ndeploy_docker.yml\nsystem_update.yml', description: 'Select an Ansible Playbook to Run')
    }
    stages {
        stage('Checkout Repository') {
            steps {
                git 'https://github.com/yourusername/ansible-projects.git'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                sh "ansible-playbook -i inventory.ini ${params.ANSIBLE_PLAYBOOK}"
            }
        }
    }
}

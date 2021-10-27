#!/bin/bash
node {
    
    stage("Build"){
    sh 'echo "Iniciando o Building"' 
    }
    
    stage("Distro Info"){
    sh '> assessment.txt'
    sh 'date +%d-%m-%y >> assessment.txt'
    sh 'echo'
    sh 'echo'
    sh 'echo "Informacoes da Distro utilizada $(hostname -i):" >> assessment.txt'
    }
    stage("Kernel Info"){
    sh 'cat /etc/*-release >> assessment.txt'
    sh 'echo "================================" >> assessment.txt'
    sh 'echo "================================" >> assessment.txt'
    sh 'echo "Informacoes do Kernel do Servidor $(hostname -i):" >> assessment.txt'
    }
    stage("Users Info"){
    sh 'uname -a >> assessment.txt'
    sh 'echo "================================" >> assessment.txt'
    sh 'echo "================================" >> assessment.txt'
    sh 'echo "Lista de Usuarios Presente no Servidor $(hostname -i):" >> assessment.txt'
    sh 'cat /etc/passwd | cut -d: -f1 >> assessment.txt'
    stage("Packages Info"){
    sh 'echo "================================" >> assessment.txt'
    sh 'echo "================================" >> assessment.txt'
    sh 'echo "Pacotes instalados no Servidor $(hostname -i):" >> assessment.txt'
    sh 'dpkg -l >> assessment.txt'
    sh 'echo "================================" >> assessment.txt'
    sh 'echo "================================" >> assessment.txt'
    }
    stage("Test"){
        sh 'cat /var/jenkins_home/workspace/desafio_pipeline/assessment.txt'
    }
    stage("Deploy"){
        sh 'echo "Compilacao Finalizada"'
    }
}

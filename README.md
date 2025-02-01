# monitora-web
Monitoração automatizada usando Prometheus+Grafana com base no projeto Pingprom https://github.com/kaihendry/pingprom

# Notas
Este projeto apenas automatiza o deploy do sistema criado por Kai Hendri (https://github.com/kaihendry/pingprom) utilizando Vagrant e Ansible
para a criação de uma maquina virtual para monitoramento de URLs

# Leia-me

1. No arquivo Targets.yml, defina quais url iram ser monitoradas.

2. Defina qual endereço IP irá utilizar no Vagrantfile (opcional).

3. Na pasta do projeto, execute o comando "vagrant up".

4. Após a execução do playbook o terminal ficará travado na ultima tarefa "Inicia Monitoramento". Isso se deve á execução do arquivo Makefile que não retorna um resultado
após a sua execução, sendo assim, o Ansible não sabe sobre a conclusão da tarefa. Algo que ainda não consegui corrigir, uma vez que o Ansible não possui na sua documentação oficial
um recurso de time out para as tarefas. Sendo assim, como paliativo, aguarde 2 minutos após o playbook executar a ultima tarefa. Feche a execução do terminal.

5. Valide o funcionamento

Prometheus http://0.0.0.0:9090

Blackbox http://0.0.0.0:9115

Alert manager http://0.0.0.0:9093

Grafana http://0.0.0.0:3000

# Referências 
https://github.com/kaihendry/pingprom

https://www.youtube.com/watch?v=Sn7Ab4EKa_c

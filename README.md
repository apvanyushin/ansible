# Самоконтроль выполненения задания

1. Где расположен файл с `some_fact` из второго пункта задания?


    ansible/group_vars/all/examp.yml

2. Какая команда нужна для запуска вашего `playbook` на окружении `test.yml`?


    ansible-playbook site.yml -i inventory/test.yml

3. Какой командой можно зашифровать файл?


    ansible-vault encrypt *path to file*

4. Какой командой можно расшифровать файл?


    ansible-vault decrypt *path to file*

5. Можно ли посмотреть содержимое зашифрованного файла без команды расшифровки файла? Если можно, то как?

    
    Можно. Мы это и проделали в ходе выполнения ДЗ. В playbook есть task debug: msg: "{{ some_fact }}", 
    мы получаем содержимое зашифрованного файла в stdout

6. Как выглядит команда запуска `playbook`, если переменные зашифрованы?


    ansible-playbook site.yml -i inventory/prod.yml --ask-vault-pass
    или
    ansible-playbook site.yml -i inventory/prod.yml --vault-password-file=*path to file*

7. Как называется модуль подключения к host на windows?


    winrm                          Run tasks over Microsoft's WinRM

8. Приведите полный текст команды для поиска информации в документации ansible для модуля подключений ssh


    ansible-doc -t connection ssh

10. Какой параметр из модуля подключения `ssh` необходим для того, чтобы определить пользователя, под которым необходимо совершать подключение?
    

    - remote_user
            User name with which to login to the remote server, normally set by the remote_user
            keyword.
            If no user is supplied, Ansible will let the SSH client binary choose the user as it
            normally.
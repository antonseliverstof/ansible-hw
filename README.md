# ansible-hw
Ansible Homework Practise

1. Запуск Playbook на окружении TEST:
	ansible-playbook site.yml -i inventory/test.yml

   Значение some_fact - 12.

2. Замена в group_vars/all значения some_facts с 12 на 'all default fact'

3. Запустил 2 контейнера как на лекции:
	docker run --name centos7 -d pycontribs/centos:7 sleep 60000
	docker run --name ubuntu -d pycontribs/ubuntu:latest sleep 60000

4. Значения фактов:
	ubuntu - deb
	centos7 - el

5. Изменил значения в group_vars для deb на deb default fact и el на el default fact.

6. Новые значения выводятся корректно

7. Зашифровал файлы с помощью Ansible-Vault:
	ansible-vault encrypt group_vars/deb/examp.yml
	ansible-vault encrypt group_vars/el/examp.yml

8. Запустил Playbook:
	ansible-playbook site.yml -i inventory/prod.yml --ask-vault-pass\
	Ansible запросил пароль.

9. Список плагинов для подключения:
	ansible-doc -t connection -l
   Подходящий для работы на control node:
	local

10. Добавил группу хостов local в prod.yml

11. Запуск Playbook, group_vars определяется верно для всех групп хостов.

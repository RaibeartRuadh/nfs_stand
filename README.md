В текущем домашнем задании реализован Vagrant стенд, поднимающий две виртуальные машины Сервер и Клиент
На стенде реализован протокол сетевого доступа к файловым системам NFS
В текущем примере обозначена директория upload в виде каталога для общего доступа.
Каталог монтируется при запуске стенда и имеет доступ на счение и запись
На стенде включен firewall, для NFS прописано правило

Файлы и каталоги:
- Файл Vagrantfile - описаны параметры для серверов стенда (IP адреса, параметры образа Centos/7) и ссылка на Ansible playbooks - general.yml
- Каталог ans_supp включает в себя файл general.yml для автоматизации поставки программного обеспечения, управление конфигурацией и развёртывание приложений под руководством Ansible, а также файл, в котором настраивается общая директория all.yml
-- general.yml - параметры для сервера и клиента: установка сервиса NFS, создание директорий, активация firewall и правила для NFS
-- all.yml - обозначение общей директории, точки монтирования и прав на доступ.

Общая директория для клиента монтируется как /opt/upload на сервере /srv/nfs/upload

При разработке и проверки стенда использовались пакеты:
- vagrant 2.2.6
- virtualbox 6.0 (или другой клиент)
- ansible 2.9.13



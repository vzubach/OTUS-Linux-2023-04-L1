# OTUS-Linux-2023-04-Lesson-1

В папке packer приминяемые скрипты для скачивания и установки образа CentOS-Stream-8-20230429, с изначальной версией ядра 4.18.0.
В процессе установки ядро автоматически обновляется до версии 6.3.1.
Создаётся и упаковывается образ centos-8-kernel-5-x86_64-Minimal.box

В VagrantFile этот образ скачивается с Vagrant Cloud и разворачивается (в конце выскакиевает какая-то косметическая ошибка но машина работает).
При подключении через vagrant ssh можно проверить что используется обновлённое ядро 6.3.1
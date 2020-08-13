# SSH Overvew & Setup

> [To Index](index.md)

## Базовые положения

Ansible по-умолчанию использует ssh-соединение.

Существует несколько способов орг-и соединения с спольз ssh. По умолчанию авторизация организована через логин/пароль. С т.зр. беопасности лучше для этой цели лучше использовать ssh ключ.

### Установка Open SSH

- SSH client на управляющем компе
- SSH server на серверах
	 - `apt-get install ssh-server`

### Генерация ключей

`ssh-keygen -t ed25519 -C "jay default"` -- для обычного соединения  
`ssh-keygen -t ed25519 -C "ancible"` -- для ансибл

- сохранить в др месте: ~/.ssh/ansible
- без п/фразы
 
 `ssh -i ~/.ssh/ansible server_ip` -- с каким ключем авторизируемся

#### Результат
**~/.ssh/**
- id_ed25519
- id_ed25519.pub

### Рассылка ключа на серверы

`ssh-copy-id -i ~/.ssh/id_ed25519.pub server_ipaddr`

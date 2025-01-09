# openvpn-setup
# Настройка и управление OpenVPN сервером

## Описание проекта

Цель проекта: Настройка безопасного VPN сервера с использованием OpenVPN для обеспечения защищенного доступа к сети.

Технологии: OpenVPN, Easy-RSA, Ubuntu/Debian, Bash, SSH.

Роль: DevOps инженер.

Основные задачи:
- Установка и настройка OpenVPN сервера.
- Генерация сертификатов и ключей с использованием Easy-RSA.
- Настройка конфигурационных файлов сервера и клиента.
- Тестирование и устранение неисправностей.
- Обеспечение безопасности и конфиденциальности данных.

## Технические детали

Установка и настройка OpenVPN:
- Установка OpenVPN и Easy-RSA на виртуальной машине.
- Генерация сертификатов и ключей для сервера и клиентов.
- Настройка конфигурационного файла сервера (server.conf).
- Настройка конфигурационного файла клиента (client1.ovpn).

Пример конфигурационного файла сервера:
`conf
port 1194
proto udp
dev tun
ca /etc/openvpn/certs/ca.crt
cert /etc/openvpn/certs/server.crt
key /etc/openvpn/certs/server.key
dh /etc/openvpn/certs/dh.pem
auth SHA256
cipher AES-256-CBC
server 10.8.0.0 255.255.255.0
ifconfig-pool-persist ipp.txt
keepalive 10 120
persist-key
persist-tun
status openvpn-status.log
verb 3
))))), [1/9/25 2:26 PM]
Пример конфигурационного файла клиента:

))))), [1/9/25 2:26 PM]
client
dev tun
proto udp
remote 51.250.42.28 1194
resolv-retry infinite
nobind
persist-key
persist-tun
remote-cert-tls server
auth SHA256
cipher AES-256-CBC
verb 3

<ca>
/etc/openvpn/certs/ca.crt
</ca>
<cert>
/etc/openvpn/certs/client.crt
</cert>
<key>
/etc/openvpn/certs/client.key
</key>

Результаты и достижения
Успешная настройка: OpenVPN сервер был успешно настроен и запущен на виртуальной машине.
Безопасность: Обеспечена безопасность и конфиденциальность данных при передаче через VPN.
Визуальные материалы
Скриншоты:

Скриншоты конфигурационных файлов.
Скриншоты командной строки с результатами выполнения команд.
Скриншоты логов сервера и клиента.
![Screenshot from 2025-01-09 14-22-17](https://github.com/user-attachments/assets/ce92f579-8bf3-4087-bf15-6d2f4ab886d7)
![Screenshot from 2025-01-09 14-29-28](https://github.com/user-attachments/assets/2cafa15d-e92e-4e79-ab5e-a80a8a7a0c5b)
![Screenshot from 2025-01-09 14-29-40](https://github.com/user-attachments/assets/439c0d24-5853-44e5-b4c1-1b4849bbf93a)

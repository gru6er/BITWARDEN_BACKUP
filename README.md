•	Скрипт делает бэкап BITWARDEN аккаунта в формате json.
•	Аутентификация происходит через API ключи, что удобно, если на аккаунте включён 2FA TOTP Authenticator.
•	Файл бэкапа шифруется в gpg файл. Что бы расшифровать файл введите команду:
echo 'your_password' | sudo gpg --batch --passphrase-fd 0 --armor --decrypt --output bw_export.json bw_export_*.json.gpg
•	Скрипт удаляет исходный, не зашифрованный файл.
•	Подразумевается, что скрипт будет работать в Cron`е, и поэтому реализовано удаление старых бэкапов.
•	Лог об последнем успешном проведении бэкапа сохраняется в папке с bitwarden. 

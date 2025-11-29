Проверить доступность ip адреса: клонировать репо и поднять бэкенд
```
sudo apt update
sudo apt -y upgrade
sudo apt install -y python3-venv
sudo apt install -y git

cd /home
git clone https://github.com/foxkodland/test-vps.git
cd test-vps

python3 -m venv my_venv
source ./my_venv/bin/activate
pip install -r requirements.txt
deactivate

sudo cp test_service.service /lib/systemd/system/
sudo systemctl daemon-reload 
sudo systemctl enable test_service.service
sudo systemctl start test_service.service

echo "Все готово, можно пробовать $(hostname -I | awk '{print $1}'):8000"
```

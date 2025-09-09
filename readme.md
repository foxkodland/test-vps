Проверить доступность ip адреса: клонировать репо и поднять бэкенд
```
sudo apt update
sudo apt -y upgrade
apt install unzip	
sudo apt install -y python3-venv
sudo apt install -y git

cd /home
git clone https://github.com/foxkodland/test-vps.git
cd test-vps

python3 -m venv my_venv
source ./my_venv/bin/activate
pip install -r requirements.txt

python main.py
```

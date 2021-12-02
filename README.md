# Node_Installation
![Project: ECU Sensing](https://img.shields.io/badge/Project-ECU%20Sensing-blueviolet)
![Type: Guide](https://img.shields.io/badge/Type-Guide-important)
![Language: C++](https://img.shields.io/badge/language-Python-blue)
![TTN: v2](https://img.shields.io/badge/TTN-v2-success)
![TTN: v3](https://img.shields.io/badge/TTN-v3-success)
Overall guidance for ECU-Sensing node deployment. 

## Installation of External Tools
sudo apt install git python3-pip -y
sudo apt-get install i2c-tools -y

## Configuration for Raspberry Pi interfaces
Enable I2c (Raspi config --> Interfaces --> I2c --> Enable --> Reset)
Enable SPI (Raspi config --> Interfaces --> SPI --> Enable --> Reset)

## Download and Organize ECU-Sensing Tools
Pull Code

	git clone https://github.com/ECU-Sensing/Raspi_Zero_Node.git

Install Dependencies
	sudo pip3 install -r Raspi_Zero_Node/requirements.txt

## Configure Instance-specific code
Fill in keys.py from TTN

Move Data files to Raspi_Zero_Node
	cp example_data_dir/data.py Raspi_Zero_Node/data.py

Install Data dependencies
	sudo pip3 install -r example_data_dir/requirements.txt

## Utilize Cron Scheduler for Automation
Open Crontab
	sudo crontab -e

Add following line to the end
	*/10 * * * *  python3 /home/pi/LoRa_Pi_Node/txrx_ttn.py


# ArgonPi4

Setup scripts for the Argon Pi4 extracted from https://download.argon40.com/argon1.sh

```
sudo raspi-gpio python-rpi.gpio python3-rpi.gpio python-smbus python3-smbus i2c-tools

sudo raspi-config nonint do_i2c 0
sudo raspi-config nonint do_serial 0

cp argononed.service /lib/systemd/system/argononed.service
sudo chmod 644 /lib/systemd/system/argononed.service

cp argononed.py /usr/bin/argononed.py
sudo chmod 755 /usr/bin/argononed.py

cp argononed.conf /etc/argononed.conf
sudo chmod 666 /etc/argononed.conf

cp argononed-power.py /lib/systemd/system-shutdown/argononed-power.py
sudo chmod 755 /lib/systemd/system-shutdown/argononed-power.py


sudo systemctl daemon-reload
sudo systemctl enable argononed.service

sudo systemctl start argononed.service
```
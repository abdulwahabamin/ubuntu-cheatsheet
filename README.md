# ubuntu-cheatsheet

#### software and update install
sudo apt-get install software-properties-gtk

#### nvidia-smi persistence mode enable
sudo nvidia-smi -i <target-gpu> -pm ENABLED

#### Running command on startup
-open terminal</br>
-sudo crontab</br>
-type '@reboot xxxx'</br>
where xxxx is the command

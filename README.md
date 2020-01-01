# ubuntu-cheatsheet

#### software and update install
sudo apt-get install software-properties-gtk

#### nvidia-smi persistence mode enable
sudo nvidia-smi -i <target-gpu> -pm ENABLED

#### Running command on startup
-open terminal</br>
-crontab -e</br>
-type '@reboot xxxx'</br>
where xxxx is the command

#### Creating a Symbolic link
- ln -s /foler/location /path/to/create/shortcut</br>

#### Installing nvidia drivers
sudo apt-get update</br>
sudo apt-get purge nvidia*</br>
sudo apt-get autoremove</br>
sudo apt-get autoclean</br>
sudo rm -rf /usr/local/cuda*</br>
sudo apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/7fa2af80.pub
echo "deb https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64 /" | sudo tee /etc/apt/sources.list.d/cuda.list</br>
sudo apt-get -o Dpkg::Options::="--force-overwrite" install cuda-10-0 cuda-drivers</br>
##### Reboot and type</br>
echo 'export PATH=/usr/local/cuda-10.0/bin${PATH:+:${PATH}}' >> ~/.bashrc</br>
echo 'export LD_LIBRARY_PATH=/usr/local/cuda-10.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}' >> ~/.bashrc</br>
source ~/.bashrc</br>
sudo ldconfig</br>
nvidia-smi</br>
tar -xf cudnn-10.0-linux-x64-v7.5.0.56.tgz</br>
sudo cp -R cuda/include/* /usr/local/cuda-10.0/include</br>
sudo cp -R cuda/lib64/* /usr/local/cuda-10.0/lib64</br>

#### Adding paths
.bashrc</br>
export PATH="/path/to/dir:$PATH"</br>
source .bashrc</br>

#### Counting number of lines in a text file
wc -l file.txt</br>

#### Counting files in a folder
ls | wc -l

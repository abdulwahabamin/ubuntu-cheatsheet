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
sudo apt-get purge nvidia* -y</br>
sudo apt-get autoremove -y</br>
sudo apt-get autoclean -y</br>
sudo rm -rf /usr/local/cuda*</br>
sudo apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/7fa2af80.pub </br>
echo "deb https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64 /" | sudo tee /etc/apt/sources.list.d/cuda.list</br>
sudo apt-get update</br>
sudo apt-get -o Dpkg::Options::="--force-overwrite" install cuda-11-0 cuda-drivers -y</br>
##### Reboot and type</br>
echo 'export PATH=/usr/local/cuda-11.0/bin${PATH:+:${PATH}}' >> ~/.bashrc</br>
echo 'export LD_LIBRARY_PATH=/usr/local/cuda-11.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}' >> ~/.bashrc</br>
source ~/.bashrc</br>
sudo ldconfig</br>
nvidia-smi</br>
tar -xf cudnn-11.0-linux-x64-v8.0.2.39.tgz</br>
sudo cp -R cuda/include/* /usr/local/cuda-11.0/include</br>
sudo cp -R cuda/lib64/* /usr/local/cuda-11.0/lib64</br>

#### Adding paths
.bashrc</br>
export PATH="/path/to/dir:$PATH"</br>
source .bashrc</br>

#### Counting number of lines in a text file
wc -l file.txt</br>

#### Counting files in a folder
ls | wc -l

#### Replacing text in a file
sed -i 's:/File/Path:/New/Dir:g' test.csv

#### Change Nvidia gpu fan speed
sudo nvidia-xconfig </br>
sudo nvidia-xconfig --cool-bits=4

#### Underclocking by changing power limit on gpu
sudo nvidia-smi -i gpu_num -pl power </br>
NOTE: Change gpu_num and power according to your gpu specs

#### Updating teamviewer
wget https://download.teamviewer.com/download/linux/teamviewer_amd64.deb </br>
sudo dpkg -i teamviewer_*.deb </br>
sudo apt-get -f install

#### Copying and renaming files
for file in *.txt; do cp $file ../comb/h_$file; done

#### Add new user and add to docker group
sudo useradd username </br>
sudo groupadd groupname </br>
sudo usermod -aG docker username </br>
sudo tail /etc/group

#### Folder access permission
change folder ownership to another group - sudo chown -R owner:groupname /path/to/folder </br>
change folder read write access (775 is read/write/execute for owner and group and read for others) - sudo chmod 775 /path/to/folder </br>

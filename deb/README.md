# For my some reasons


I just download it from docker and put this deb to github

	locate *.deb # to find my current deb
	

Clean old version of docker
============

Pre install
========

	sudo apt-get install nvidia-cuda-toolkit
	sudo apt-get install nvidia-settings
    sudo apt purge nvidia-*
    sudo add-apt-repository ppa:graphics-drivers/ppa
    sudo apt update
    # find the latest version of nvidia- .
    # sudo apt-get search nvidia-..
    sudo apt install nvidia-387

Pre set
========

    sudo service lightdm stop
    sudo init 3


    vim /etc/modprobe.d/blacklist-nouveau.conf
    # put following inside the file
    blacklist nouveau
    options nouveau modeset=0

    # regernerate
    sudo update-initramfs -u
    sudo reboot
    
    # ================

Test Cuda
=======

	docker run --runtime=nvidia --rm nvidia/cuda:8.0 nvidia-smi
	docker run --runtime=nvidia --rm nvidia/cuda:8.0-devel nvidia-smi

Ref
=======
	# Install nvidia
	https://github.com/NVIDIA/nvidia-docker	

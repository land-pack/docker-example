# For my some reasons


I just download it from docker and put this deb to github

	locate *.deb # to find my current deb
	

Clean old version of docker
============

Pre install
========

	sudo apt-get install nvidia-cuda-toolkit
	

Test Cuda
=======

	docker run --runtime=nvidia --rm nvidia/cuda:8.0 nvidia-smi
	docker run --runtime=nvidia --rm nvidia/cuda:8.0-devel nvidia-smi

Ref
=======
	# Install nvidia
	https://github.com/NVIDIA/nvidia-docker	

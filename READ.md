#docker-world
A. Docker Installation Guide
OS requirements
To install Docker, you need the 64-bit version of one of these Ubuntu versions:
	•	Yakkety 16.10
	•	Xenial 16.04 (LTS)
	•	Trusty 14.04 (LTS)
Docker CE is supported on both x86_64 and armhf architectures.
Uninstall old versions
Older versions of Docker were called docker or docker-engine. If these are installed, uninstall them:
$ sudo apt-get remove docker docker-engine
It’s OK if apt-get reports that none of these packages are installed.
The contents of /var/lib/docker/, including images, containers, volumes, and networks, are preserved. The Docker CE package is now called docker-ce, and the Docker EE package is now called docker-ee.
Recommended extra packages for Trusty 14.04
Unless you have a strong reason not to, install the linux-image-extra-* packages, which allow Docker to use the aufs storage drivers.
$ sudo apt-get update
$ sudo apt-get install \
    linux-image-extra-$(uname -r) \
    linux-image-extra-virtual
Install Docker
You can install Docker in different ways, depending on your needs:
	•	Most users set up Docker’s repositories and install from them, for ease of installation and upgrade tasks. This is the recommended approach.
	•	Some users download the DEB package and install it manually and manage upgrades completely manually. This is useful in situations such as installing Docker on air-gapped systems with no access to the internet.


	Short Docker Installation Guide

Docker CE 
1.Install packages to allow apt to use a repository over HTTPS: 
	$ sudo apt-get install  apt-transport-https ca-certificates curl software-properties-common 
2.Add Docker’s official GPG key: 
	$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
 Verify that the key fingerprint is 9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88. 
	$ sudo apt-key fingerprint 0EBFCD88 pub 4096R/0EBFCD88 
3.Use the following command to set up the stable repository. You always need the stable repository, even if you want to install edge builds as well. 
amd64: 
	$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
4.Install Docker 
	$ sudo apt-get update && apt-get install docker-ce


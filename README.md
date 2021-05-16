# Torclient-install-ubuntu
How to install tor client on ubuntu 20.04 LTS

(run as sudo or root, and run "apt update" before running any command)
1- apt install apt-transport-https curl
2- echo "deb https://deb.torproject.org/torproject.org/ $(lsb_release -cs) main" > /etc/apt/sources.list.d/tor.list
3- curl https://deb.torproject.org/torproject.org/A3C4F0F979CAA22CDBA8F512EE8CBC9E886DDD89.asc | gpg --import
4- gpg --export A3C4F0F979CAA22CDBA8F512EE8CBC9E886DDD89 | apt-key add -
5- apt update
6- apt install tor tor-geoipdb torsocks deb.torproject.org-keyring

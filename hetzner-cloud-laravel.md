# Installation

## Step 0 – Setup SSH-Key When creating Server

## Step 1 – Installing the Nginx Web Server

```
sudo apt update
sudo apt install nginx
```

Enable `Ngix` by `ufw` by typing:

```
sudo ufw allow 'Nginx HTTP'
sudo ufw status
```
### Find Domain Name Pointed to Server

If you do not have a domain name pointed at your server and you do not know your server’s public IP address, you can find it by running the following command:

```
ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'
```

[Digital Ocean - Nginx Web Server](https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-ubuntu-18-04)

## Step 2 – Install Composer

```
sudo apt update
sudo apt install curl php-cli php-mbstring git unzip

cd ~
curl -sS https://getcomposer.org/installer -o composer-setup.php
```

Copy the hash from that page and store it as a shell variable:

`HASH=544e09ee996cdf60ece3804abc52599c22b1f40f4323403c44d44fdfdd586475ca9813a858088ffbc1f233e9b180f061` 

Make sure that you substitute the latest hash for the highlighted value.

Now execute the following PHP script to verify that the installation script is safe to run:

`php -r "if (hash_file('SHA384', 'composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"`
 
You’ll see the following output.

```
Installer verified
```

To install composer globally, use the following command which will download and install Composer as a system-wide command named composer, under `/usr/local/bin`:

```
sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
```
 
Check if composer is working:

`composer`

[DigitalOcean - Install composer](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-composer-on-ubuntu-18-04)

## Step 3 – Login to your server

* Go to the server list in console cloud and copy your server's IP address (e.g. `10.0.0.1`)
* Open your terminal and write `# ssh root@10.0.0.1`
* You will see now welcome message from your server




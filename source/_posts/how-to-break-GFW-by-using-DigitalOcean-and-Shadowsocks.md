title: how to break GFW by using DigitalOcean and Shadowsocks?
date: 2016-01-15 15:25:20
categories: 
- IT  
tags: 
- GFW
- DigitalOcean
- Shadowsocks
---
You can follow along with this tutorial.In this way you finally breaok the GFW, access everything you want from china.
# Get Started
OK, let's go!
# Register DigitalOcean and get a cloud host
DigitalOcean, Inc. is an American internet services provider based in New York City. The company leases capacity from existing data centers, including sites in New York, Amsterdam, San Francisco, Toronto, London, Singapore and Frankfurt. 
1. visit the DigitalOcean'shomepage and sign up a account  
2. bind your credit card of bank or use paypal and pay at least 5 (a one-time payment that will not recur), then you can use promo code if you have its  
3. create droplet
+ choose an image(distrutions or Apps), i opted for ubuntu
+ choose a size(a package deal), minium: 5$/mo, enough
+ choose a datacenter region, San Francisco(good, ave 250ms)
+ Create SSH Key(optional)
 + check available sshkey 
    ```
    cd ~/.ssh
    ls *.pub
    ```
 + if nothing is ouputed, you need a new sshkey
      ```
      ssh-keygen -t rsa -C "email@example.com"
     ```
 + Once you run the upside command, you  will see the info followed:
    
   ```
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/you/.ssh/id_rsa): [Press enter]
Enter passphrase (empty for no passphrase): [Type a passphrase]
Enter same passphrase again: [Type passphrase again]
Now your SSH key will be generated.
Your identification has been saved in /Users/your_username/.ssh/id_rsa.
Your public key has been saved in /Users/your_username/.ssh/id_rsa.pub.
The key fingerprint is:
01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db email@example.com
  ```
 + the pub key is located in /Users/Jerry/.ssh/id_rsa.pub, you can open and copy it to DO.
+ make it.
+ you will get a droplet which  info will be shown: ip/cpu/distrution/...
   
# Install shadowsocks on digitalocean server
 1. login your  droplet
 2. change your default password
 3. update depencies
  ```
  apt-get update
  ```
  
 4. install shadowsocks
In the enviorment of Debian / Ubuntu: 
  ```
  apt-get install python-pip
  pip install shadowsocks
  ```
In the enviorment of CentOS:
  ```
  yum install python-setuptools && easy_install pip
  pip install shadowsocks
  ```
 5. config the  shadowsocks server
   ```
vi /etc/shadowsocks.json
add:
{
    "server":"ip address",
    "server_port":8388,
    "local_address": "127.0.0.1",
    "local_port":1080,
    "password":"your password",
    "timeout":300,
    "method":"aes-256-cfb",
    "fast_open": false
}
 ```
 
 6. start the servers:
```
ssserver -c /etc/shadowsocks.json -d start
ssserver -c /etc/shadowsocks.json -d stop
```

# Install and use shadowsocks client on mobile phone/windows/linux 
It's very simple, download clients, install them, configure them, and enjoy them. 

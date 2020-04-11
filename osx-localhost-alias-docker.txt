https://stackoverflow.com/questions/22944631/how-to-get-the-ip-address-of-the-docker-host-from-inside-a-docker-container

add
sudo ifconfig lo0 alias 10.9.8.7

test
telnet 10.9.8.7 9000

remove
sudo ifconfig lo0 -alias 10.9.8.7

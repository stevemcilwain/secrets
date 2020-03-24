# Setup tor hosting

1) Edit /etc/tor/torrc
2) Uncomment HiddenServiceDir, HiddenServicePort
3) service tor restart
4) php -S 127.0.0.1:80
5) cat /var/lib/tor/hidden_service/hostname

Browse by starting tor and visiting the .onion site.
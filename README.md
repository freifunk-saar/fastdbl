# fastdbl

ffsaar fastd Blacklist (based on ffrl! Thanks!)

Public keys listed are no longer accepted for connecting to our Networks, as a result of abuse, faulty interconnecting different Networks, and so on

Installation:

1 - cron-wget the blacklist to your fastd directory:

    crontab -e

then add 

    */5 * * * * wget -q -O /etc/fastd/fastdbl/fastd-blacklist.json https://raw.githubusercontent.com/freifunk-saar/fastdbl/master/fastd-blacklist.json

or use salt.

2 - download the Scipt and make it Xecutable:

    wget -O /etc/fastd/fastdbl/fastd-blacklist.sh https://raw.githubusercontent.com/freifunk-saar/fastdbl/master/fastd-blacklist.sh
    chmod +x /etc/fastd/fastdbl/fastd-blacklist.sh

3 - Add the following to your fastd.conf:

    on verify "
      /etc/fastd/fastdbl/fastd-blacklist.sh $PEER_KEY
    ";

4 - restart your fastd and you are ready to go:

    /etc/init.d/fastd restart
    

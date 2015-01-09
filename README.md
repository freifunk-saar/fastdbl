# fastdbl

ffrl fastd Blacklist

Public keys listed are no longer accepted for connecting to our Networks, as a result of abuse, faulty interconnecting different Networks, and so on

Installation:

1 - cron-wget the blacklist to your fastd directory:

  crontab -e

then add 

  */5 * * * * wget -q -O /etc/fastd/fastd-blacklist.json https://raw.githubusercontent.com/ffruhr/fastdbl/master/fastd-blacklist.json

2 - download the Scipt and make it Xecutable:

  wget -O /etc/fastd/fastd-blacklist.sh https://raw.githubusercontent.com/ffruhr/fastdbl/master/fastd-blacklist.sh
  chmod +x /etc/fastd/fastd-blacklist.sh

3 - Add the following to your fastd.conf:

  on verify "
    /etc/fastd/fastd-blacklist.sh $PEER_KEY
  ";

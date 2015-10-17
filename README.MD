# (Really simple) Internet Connection Tester

This script will keep a record of up/down state of your internet connectivity.

It completelly ignores router issues or other connectivity problems. 

It is just a plain [f]ping to a well know IP address which append log entries to a file on a Dropbox directory.

Based on the work of Rafael from http://askubuntu.com/questions/27954/how-can-i-check-internet-connectivity-in-a-console.

1 - Install fping:
```
sudo apt-get install fping
```

2 - Copy the testcon script to /etc/init.d:
```
sudo cp testcon /etc/init.d
```

3 - Edit the testcond script (at least the LOGFILE entry):
```
(...)
TARGET=8.8.8.8
TIMEOUT=60
VERBOSE=false
LOGFILE=/home/<USER>/Dropbox/Aplications/testcon/internet_log.txt
(...)
```

4 - Copy the testcond script to /etc/init.d:
```
sudo cp testcond /etc/init.d
```

5 - Configure the testcon to start on boot:
```
sudo update-rc.d testcon defaults
sudo update-rc.d testcon enable
```

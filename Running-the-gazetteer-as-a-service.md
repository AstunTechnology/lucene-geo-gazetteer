To run this as a systemd service in your Linux evironment that starts on boot you will need to:

* create a `myservice.service` file located at `/etc/systemd/system/myservice.service`
* have the following inside the `myserive.service` file:

```
[Unit]
Description=GeoParser server service

[Service]
Type=simple
ExecStart=some/location/lucene-geo-gazetteer/src/main/bin/lucene-geo-gazetteer -server
Restart=always
TimeoutStartSec=0

[Install]
WantedBy=default.target
```

* once this is set you need to run the following commands to enable and start the service for the first time:

```
sudo systemctl enable myservice
sudo systemctl start myservice
```

If you want to test that the service is running you can run the following command:

`sudo systemctl status myservice` 

and the output you should see should be similar to:

```
● gazetteer-server.service - GeoParser server service
   Loaded: loaded (/etc/systemd/system/gazetteer-server.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2022-11-21 15:54:44 UTC; 38min ago
 Main PID: 1266 (lucene-geo-gaze)
    Tasks: 25
   Memory: 154.6M
   CGroup: /system.slice/gazetteer-server.service
           ├─1266 /bin/bash /home/astun/lucene-geo-gazetteer/src/main/bin/lucene-geo-gazetteer -server
           └─1274 java -cp /home/astun/lucene-geo-gazetteer/src/main/bin/../../../target/lucene-geo-gazetteer-0.3-SNAPSHOT-jar-with-dependencies.jar edu.usc.ir.geo.gazett...
```
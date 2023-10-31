## Getting started
Please run the **setup.sh** script to install the scripts and services. You can safely run this script as many times as needed.

## Services
**dds-agent.service** <br>
This service starts the DDS agent which connects with the PX4 uXRCE-DDS-Client. `Telem1` on the flight controller is connected directly to the Jetson UART `/dev/ttyTHS0`. This service depends on the `systemd-timesyncd` service to synchronize system time with an accurate remote reference time source.

**jetson-can.service** <br>
This service enables the Jetson CAN interface.

**jetson-clocks.service** <br>
This service fixes the Jetson clocks to their maximum rate.

**mavlink-router.service** <br>
This service enables mavlink-router to route mavlink packets between endpoints. The **main.conf** file defines these endpoints and is installed at **/etc/mavlink-router/**.

## Scripts
The files in the scripts directory get installed directly to **/usr/bin** on the Jetson.

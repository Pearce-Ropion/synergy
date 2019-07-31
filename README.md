# Synergy

Synergy is an Energy Monitoring and Visualization PLatform designed to allow anyone, large or small to monitor the electrical energy usage.

## Packages
Synergy is made up for 5 key components:

* [Synergy UI][synergy-ui]
  - The user interface, configuration manager and visualization platform
  - Built on a React.js Core and integrated with Redux, Axios and Nivo Charts
* [Synergy API][synergy-api]
  - The backend designed to intreface with the frontend UI
  - Built on an Express.js platform and supports realtime data streams with socket.io
* [Synergy Manager][synergy-manager]
  - The backend designed to interface with the individual monitoring systems
  - Built using Python and a combines realtime MQTT data transfer with SVM Machine Learning Models to process and predict energy usage patterns
* [Synergy Monitor][synergy-monitor]
  - The monitoring system designed to run on an small computing device such as a Raspberry Pi or Arduino
  - Built on Python and MQTT to transfer realtime energy usage statistics about connected devices to the Synergy Manager
* [Synergy DB][synergy-db]
  - Synergy's database compnent that manages realtime data as well as configuration settings for the system
  - Built using MySQL relational tables

## Getting Started
In addition to the above libraries, Synergy makes use of the following hardware components:
* Central Server (1 or more) to host the Synergy manager, API and UI
* Individual computing devices which can include but are not limited to devices like the Raspberry Pi and Arduino boards
* Individual monitoring devices that allow for real time monitioring of the current used by connected devices
  - Synergy is currently desgined to be integrated with a [NCD AC Current Monitor with IoT][ac-monitor] of any size
  - However, the simplicity of the Synergy Monitor component allows for any monitoring device to be intregrated with minor code changes
  - The only requirement being that the manager accepts MQTT messages with a specific format
* An accessible wifi network to which all of the devices are connected
  
Once you have all of the hardware components, you can clone this repository which makes use of git submodules
`git clone --recursive --jobs 6 https://github.com/Pearce-Ropion/synergy.git`

If you have already cloned the repo, you can fetch all of the submodules using
`git submodule update --init --recursive --jobs 8`


[ac-monitor] https://store.ncd.io/product/8-channel-on-board-95-accuracy-20-amp-ac-current-monitor-with-iot-interface/
[synergy-ui] https://github.com/synergy-scu/synergy-ui
[synergy-api] https://github.com/synergy-scu/synergy-api
[synergy-manager] https://github.com/synergy-scu/synergy-manager
[synergy-monitor] https://github.com/synergy-scu/synergy-monitor
[synergy-db] https://github.com/synergy-scu/synergy-db


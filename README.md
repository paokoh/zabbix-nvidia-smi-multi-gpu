# zabbix-nvidia-smi-multi-gpu
A zabbix template using nvidia-smi. Works with multiple GPUs on Windows and Linux. 

## Features: 

- low-level discovery of all the graphics cards
- item prototypes for:
  - fan speed
  - total, free and used memory
  - power draw in decaWatts (tens of Watts, so that it can fit in the graphs nicely)
  - temperature
  - utilization
- a graph prototype having the fan speed, power draw and temperature in one graph
- trigger prototypes set at different GPU temperatures
- a batch script for low-level discovery on Windows
- a BASH script for low-level discovery on Linux

Events caused by the triggers:
![Triggers:](https://steemitimages.com/DQmNbgRSxa7LRbaaJszCdHbDEPM5wwCpKGUFJtibWEsBwTY/image.png)

And the graphs: 
![Graphs](https://steemitimages.com/DQmPSwfNoERQ13wrR8YeqdjSfDJpAiECXKSMzUjwaoLYkaG/image.png)

This is essentially a multi-GPU rewrite of RichardKav's template, as found here: https://github.com/RichardKav/zabbix-nvidia-smi-integration/

## On Linux: 

The following UserParameters need to be added to the zabbix-agent configuration: 
* Add the contents of the file `userparameter_nvidia-smi.conf.linux` to your zabbix_agentd.conf file.
* The get_gpus_info.sh file should be put in /etc/zabbix/scripts/ and made executable by running ```chmod +x get_gpus_info.sh```

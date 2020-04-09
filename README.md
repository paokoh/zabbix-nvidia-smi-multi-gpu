# zabbix-nvidia-smi-multi-gpu
该zabbix模板可以自动发现并监控多个Nvidia GPU（依赖nvidia-smi），暂只支持Linux。 

## 功能: 

- 自动发现所有GPU
- 监控项目:
  - GPU型号
  - GPU使用率
  - 显存总量, 显存可用 和 已用显存

## Linux 系统: 

需要将用户自定义参数文件添加到zabbix: 
* 拷贝文件 `linux_gpu_nvidia.conf` 到/etc/zabbix/zabbix_agentd.d/
* 然后从zabbix界面上导入模板文件linux_gpu_nvidia_templates.xml

修改自 https://github.com/plambe/zabbix-nvidia-smi-multi-gpu ，改进为不需要使用sh脚本文件执行自动发现。

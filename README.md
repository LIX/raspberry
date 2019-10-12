# raspberry
用户名:pi 密码：raspberry 
vcgencmd measure_temp 测量温度
reboot 重启
cat /proc/cpuinfo cpu信息
cat /proc/meminfo 内存信息
iwconfig
iwlist wlan0 scan 搜索wifi
wpa_passphrase SSID名称 密码

#配置wifi
allow-hotplug wlan0  
auto wlan0  
iface wlan0 inet dhcp  
pre-up wpa_supplicant -B w -D wext -i wlan0 -c /etc/wpa_supplicant/wpa_supplicant.conf  
post-down killall -q wpa_supplicant

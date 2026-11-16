// Как настроить логирование на D-Link 1100-10 ME A1.  

enable syslog  
create syslog host 1 ipaddress 10.245.2.210 severity all facility local0 udp_port 514 state enable  
config log_save_timing on_demand  
enable command logging // логирование команд пользователя  

// SNTP (Simple Network Time Protocol)  
// Простой протокол сетевого времени - это упрощённая версия NTP, предназначенная для  
// синхрона системного времени устройств по сети.  

config time_zone operator + hour 7 min 0  
config sntp primary 10.6.37.21 secondary 10.6.36.38 poll-interval 720  
enable sntp  
config dst disable  

show time // проверяем время, оно должно совпадать с реальным временем того города, где мы настраиваем коммут.  

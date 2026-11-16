// Включаем SNMP.  
// SNMP (Simple Network Management Protocol) - простой протокол сетевого управления.  
// Нужен для мониторинга и управления различными устройствами, в т.ч. маршрутизаторами и коммутами.  

enable snmp  
enable snmp traps  
enable snmp authenticate_traps  
enable snmp linkchange_traps  
config snmp linkchange_traps ports all enable  

// Удаляем старые настройки.  

delete snmp community public  
delete snmp community private  
delete snmp user ReadOnly v1  
delete snmp user ReadWrite v1  

// Создаём собственные коммьюнити и указываем ip-адреса серверов,  
// принимающих трапы. Поднимаем ключи, одним словом...  

create snmp community fVy9kKyad2zvZnm ReadOnly  
create snmp community b5brXVFNR8mJsZr ReadWrite  

create snmp host 10.245.2.210 v2c fVy9kKyad2zvZnm  

// Настраиваем mac-notification  

enable mac_notification  
config mac_notification interval 1  
config mac_notification historysize 1  

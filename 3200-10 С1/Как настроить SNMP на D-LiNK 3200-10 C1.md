// Включаем сам SNMP, везде должно быть success.  
// SNMP - Мониторинг и управление.  

enable snmp traps  
enable snmp  
enable snmp authenticate_traps  
enable snmp linkchange_traps  
config snmp linkchange_traps ports all enable  

// Дальше 9 команд. Удаление групп.  
// При попытке удалить не существующую, напишет: такой группы не существует.  

delete snmp community public  
delete snmp community private  
delete snmp group public  
delete snmp group private  
delete snmp group ReadGroup  
delete snmp group WriteGroup  
delete snmp group initial  
delete snmp view restricted all  
delete snmp user initial  

// Создаём ключи, чтобы подтянулась служба мониторинга.  

create snmp community fVy9kKyad2zvZnm view CommunityView read_only  
create snmp community b5brXVFNR8mJsZr view CommunityView rear_write  

// Врубаем обнаружение железяк, подключенных/отключенных от коммутатора.  

config mac_notification interval 1 historysize 1  
enable mac_notification  

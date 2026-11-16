// Глобально включаем LLDP на коммутаторе D-LiNK 1100-10 ME A1.  
// Версия прошивки 1.01.B102  

enable lldp  
config lldp message_tx_interval 30  
config lldp tx_delay 2  
config lldp message_tx_hold_multiplier 4  

// Расширенная настройка LLDP, оптимизация, информативность.  

config lldp ports all notification disable  
config lldp ports all basic_tlvs all enable  
config lldp ports all dot1_tlv_pvid enable  
config lldp ports all dot1_tlv_protocol_identity eapol enable  
// Здесь вместо all пишем eapol. eapol следит за тем, чтобы кто угодно не мог воткнуть что угодно и откуда угодно.  
config lldp ports all dot3_tlvs all enable  
config lldp ports all mgt_addr ipv4 auto enable // здесь, судя по всему, надо вводить ip-шник управления.  

// show lldp remote_ports // смотрим соседей по LLDP.  

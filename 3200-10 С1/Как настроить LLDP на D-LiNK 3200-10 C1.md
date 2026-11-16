// Глобально включаем LLDP на коммутаторе.  
// LLDP - это обнаружение соседей.  

enable lldp  
config lldp message_tx_interval 30  
config lldp tx_delay 2  
config lldp message_tx_hold_multiplier 4  

// Расширенная настройка LLDP, оптимизация и информативность.  

config lldp ports all notification disable  
config lldp ports all dot1_tlv_vlan_name vlanid 1-4094 enable  
config lldp ports all dot1_tlv_pvid enable  
config lldp ports all dot3_tlvs all enable  
config lldp ports mgt_addr ipv4 <mgmt-ip> enable // здесь нужно прописать управляющий ip-шник.  

// show lldp remote_ports - покажет соседей по lldp.  

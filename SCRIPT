# NO-IP Mikrotik Script

Configuração do Script 

:local NOIPUser "LOGIN"
:local NOIPPass "SENHA"
:local NOIPDomain "DOMINIO.ddns.net"

:global currentIP [/ip cloud get public-address]

:if ([:resolve $NOIPDomain] = $currentIP) do={
      #/tool fetch mode=http user=$NOIPUser password=$NOIPPass url="http://dynupdate.no-ip.com/nic/update\3Fhostname=$NOIPDomain&myip=$currentIP" keep-result=no
	  /tool fetch mode=http url="http://$NOIPUser:$NOIPPass@dynupdate.no-ip.com/nic/update?hostname=$NOIPDomain&myip=$currentIP" keep-result=no
      :log info "NO-IP Update: $NOIPDomain - $currentIP"
}
